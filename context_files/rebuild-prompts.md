# Rebuilding the refresh pipeline with an AI assistant

The original scrapers, transcript pipeline and refresh workflow ran on the previous owner's machine and weren't handed over as code. Instead of maintaining old scripts, this file gives you **prompts**. Paste each one into an AI coding assistant (Claude Code, Cursor, Copilot agent mode, or similar) and it will build the piece for your environment.

**You don't need any of this to keep the bot running.** See Option A in [`how-to-update.md`](how-to-update.md). Rebuild the pipeline only if you want the bot to keep up with website, docs and release changes without manual tracking.

## Before you start

- **Recommended order:** Prompt 0 → 1 → 2 → 5. Prompts 3 and 4 are optional. With 0, 1, 2 and 5 you get about 80% of the value: the bot stays in step with docs, website and releases.
- **Run each prompt in a fresh session**, from the folder you create in Prompt 0.
- **Review what the assistant builds before you schedule anything.** Run each scraper once by hand and open its output.
- The prompts describe *what* to build and *what went wrong before*. The assistant picks libraries and structure. Expect to adjust them: websites change.

---

## Prompt 0: workspace layout

```text
Set up a local workspace for maintaining the GeoDin website chatbot's knowledge base.

Create this folder layout (pick a parent folder outside any git repo):

geodin-knowledge/
  sources/
    scraping/docs/          # output of the docs.geodin.com scraper
    scraping/website/       # output of the geodin.com scraper
    scraping/marketplace/   # Autodesk Marketplace listing snapshot
    scraping/support/       # optional: support.geodin.com (German)
    transcripts-anonymized/ # optional: anonymized customer-call transcripts
    transcript-knowledge/   # optional: insights extracted from transcripts
    curated/                # hand-written notes: competitors, partners
    published-articles/     # only articles that are actually published
  tools/                    # scraper and refresh scripts, each with its own venv
  state/                    # refresh manifest (source hashes) — never commit to the public repo

Also clone https://github.com/geodin-hq/geodin-chatbot-knowledge next to it.
Read its context_files/README.md and context_files/how-to-update.md so you
understand the architecture before we build anything.

Rules for everything we build here:
- Python, one virtual environment per tool, no global installs.
- Every scraper builds its output in memory first and only overwrites files after
  the whole crawl succeeded and the page count looks sane (abort if it drops
  sharply vs. the last run). Never delete outputs before a successful crawl.
- Output is clean markdown, one file per logical bucket, with the source URL
  above each page's content so later edits can cite it.
- Keep a small scrape log (JSON) with timestamp + page count per source.
```

---

## Prompt 1: docs.geodin.com scraper (product and technical facts)

```text
Build a scraper for the GeoDin documentation site that writes markdown into
sources/scraping/docs/.

Site facts:
- It is a GitBook site with three English sitemaps:
    https://docs.geodin.com/sitemap-pages.xml                 -> docs-geodin-core.md
    https://docs.geodin.com/geodin-ground/sitemap-pages.xml   -> docs-geodin-ground.md
    https://docs.geodin.com/geodin-onsite/sitemap-pages.xml   -> docs-geodin-onsite.md
  (Desktop shares Core's English content; no separate file needed.)
- Plain HTTP + HTML parsing is enough (requests + BeautifulSoup + markdownify).
  Take the page title from <h1>, content from <main> (fall back to <article>).
- Also write docs-index.md: every page with URL and a one-line summary, plus counts.

Clean-up the previous version had to do (check whether still needed):
- Strip GitBook boilerplate: "Previous"/"Next" navigation links, footer
  artifacts, the llms.txt notice injected at the top of pages, and the
  "GitBook Assistant" widget text, which can appear at any indentation, inside
  blockquotes, or glued to code-block toolbars ("GitBook AssistantAskCopy").
- Verify afterwards: no "[Previous", "[Next", "GitBook Assistant" or "llms.txt"
  strings left in output.

Expected size in late 2026: roughly 180 pages total. Warn if the count drops.
Report pages per product and any failed URLs.
```

---

## Prompt 2: geodin.com and Autodesk Marketplace scraper (positioning, pricing page, releases)

```text
Build a scraper for www.geodin.com plus the GeoDin Ground listing on the
Autodesk Marketplace. Output markdown into sources/scraping/website/ and
sources/scraping/marketplace/.

geodin.com:
- Source: https://www.geodin.com/sitemap.xml. Keep English URLs only (drop /de/*).
- Drop Shopify leakage: /vendors/*, /product-types/*, /collections/*, /tags/*,
  /products/*, and /privacy-policy.
- Use a headless browser (Playwright + Chromium): prices on /pricing are
  injected by JavaScript and a plain HTTP fetch misses them. Accept the cookie
  banner on first load.
- It is a Webflow site. Strip real site navigation/footers/repeated CTAs, BUT keep
  accordion/FAQ bodies: Webflow renders them as <nav class="w-dropdown-list">,
  which a naive "remove all <nav>" deletes. Check /release-notes: every version
  must be followed by its "what changed" text, not only version + date.
- Bucket pages into files:
    geodin-website-suite.md         home, suite, product pages, features, integrations
    geodin-website-industries.md    /industries/*
    geodin-website-alternatives.md  /alternative-for and /alternative-for/*
    geodin-website-case-studies.md  /case-studies/*, /blog-posts/*, /newsroom
    geodin-website-company.md       about, pricing, locations, contact, demo/training, release notes
    geodin-website-index.md         every page + one-line summary + counts per bucket
- Abort without writing if fewer than ~10 pages were crawled (expect 40+).

Autodesk Marketplace (GeoDin Ground plugin for Civil 3D):
- URL: https://marketplace.autodesk.com/apps/e980e6d6-57f3-4de3-b311-0da8181b0ff6
- Output: sources/scraping/marketplace/autodesk-marketplace-geodin-ground-listing.md
- It is a JavaScript single-page app: "networkidle" never fires, so use
  domcontentloaded + explicit waits. Capture the Details fields (current
  version, Civil 3D compatibility) and the description.
- The FULL version history (every release with its notes) is only in a modal
  that opens when you click the version number. Open it and parse it.
- If a capture comes back without version history or suspiciously short, keep
  the previous snapshot instead of overwriting it.
- Preserve anything below a "HUMAN NOTES BELOW" marker line across runs.
- Why this matters: this listing was repeatedly the first public place a new
  Ground release or Civil 3D version appeared, ahead of geodin.com and the docs.
```

---

## Prompt 3 (optional): support.geodin.com (German help center)

```text
Build a fetcher for the GeoDin support help center (Zendesk, German) that writes
markdown into sources/scraping/support/.

- The help-center web pages block bots (403), but the public Zendesk API works:
    https://support.geodin.com/api/v2/help_center/de/categories.json
    https://support.geodin.com/api/v2/help_center/de/sections.json
    https://support.geodin.com/api/v2/help_center/de/articles.json
  Follow pagination. Article bodies come back as HTML in the JSON; convert to markdown.
- Output: support-index.md (category -> section -> article, with html_url and
  updated date) and one support-<category-slug>.md per category with all bodies.
- German content is expected. Build everything in memory, write only on success.
- Around 70 articles in 4 categories as of mid-2026.
```

Note: this source was **never** connected to the chatbot refresh. Adding it is your call. The "Das Neueste" (latest news) category carries release announcements.

---

## Prompt 4 (optional): customer-call transcripts to commercial insight

Only do this if you have recordings or transcripts of trainings and demos, and permission to use them.

```text
Build a two-stage pipeline for GeoDin training/demo call transcripts.

Stage 1 — anonymize (one transcript at a time):
- Input: a .docx or .txt transcript. Before any full-text analysis, ask me for
  the client/company name and the person names, and do a blind case-insensitive
  find-and-replace to [CLIENT] / [PERSON_1]... Then scan for any remaining
  names, companies, emails, phone numbers and replace them too.
- Keep all product and technical content.
- Save to sources/transcripts-anonymized/ as YYYY-MM-DD_<type>_<topic-slug>.txt
  where type is training or demo. No client names in the filename.

Stage 2 — extract commercial insight (only for new transcripts, tracked by a manifest):
- From the anonymized transcripts, extract what documentation will never carry:
  pain points, use cases by industry, migration stories (prior tool, trigger,
  friction), competitive encounters, voice-of-customer language, feature requests
  (with transcript + timestamp + short quote), and docs-gap signals (recurring
  how-to questions — the question only, never the answer).
- Skip product how-to content, small talk, internal chatter, any names.
- Product names: "GeoDin", "GeoDin Ground", "GeoDin Onsite" (normalize
  "GeoDin Core"/"GeoDin Desktop" to "GeoDin"; never just "Ground" or "Onsite").
- Write per-transcript extractions to an intermediate folder (prefix it with "_"
  so the refresh ignores it), then always rebuild these merged, deduplicated files
  in sources/transcript-knowledge/:
    pain-points.md, use-cases-by-industry.md, migration-stories.md,
    competitive-encounters.md, voice-of-customer.md, feature-requests.md,
    docs-gap-signals.md
```

---

## Hand-curated sources (no prompt, just keep them up to date)

Some of the most valuable input was written by hand. Recreate it as you learn things:

- **`curated/` competitor notes.** One file per competitor, each covering what they offer, where GeoDin wins, honest trade-offs and migration talking points. Competitors covered so far: gINT, OpenGround, BoreDM, Geolabor, and for field apps Aldoa, eFieldData, GEO5 Data Collector and OpenGround Data Collector. Also partnership notes (Autodesk, Esri, the Symetri reseller partnership) and the "ground truth" core differentiator.
- **`published-articles/`.** Only articles that are actually live on a third-party site. Never drafts: a draft that reaches the bot gets quoted to customers as fact.

Keep in mind that these are snapshots. Put the date at the top of each file.

---

## Prompt 5: the refresh workflow (sources to PR)

```text
Build a refresh workflow that keeps the geodin-chatbot-knowledge repo in sync with
the source folders under sources/. Read context_files/README.md and
context_files/how-to-update.md in the repo first — they define the rules.

Behaviour:
1. Pre-flight: repo on main, pulled, working tree clean. Stop otherwise.
2. Drift detection: walk the watched source folders recursively (.md files;
   skip .DS_Store, Office lock files "~$*", and anything starting with "_").
   SHA-256 each file and compare with state/manifest.json, which records the
   hashes as of the last MERGED refresh. Report added / changed / removed per
   folder and let me choose which to process. First run = everything is "added".
   Also keep a copy of each source file as of the last merge, so the next
   run can show real old-vs-new diffs instead of only "changed".
3. Proposals: read ALL brain files + Central_Reference.md (about 160 KB, fits in
   context) plus the changed sources (or their diffs). Decide per change which
   files it affects — no fixed topic map. Output proposals grouped by file:
   File / Type (Update|Add|Remove) / Where (heading) / Why / Source / Proposed text.
   - Facts -> the matching Part1_/Part2_ file.
   - Behaviour, tone, competitor handling, pricing policy, qualification rules
     -> Central_Reference.md §2; urgent overrides -> §5 (dated).
   - Never propose edits to System_Prompt.md (stale copy; the live prompt is in n8n).
     If the live prompt needs changing, write a note for the n8n owner instead.
   - Never edit Part2_ChatbotIntel_Guardrails.md or
     Part2_ChatbotIntel_Handoff_Protocol.md; raise a manual-review note instead.
   - Apply the source-precedence rules from how-to-update.md. Treat "planned",
     "under development", "targeted for" as NOT live.
   - For every fact you change, search the whole repo for other copies and
     propose fixing all of them.
   If more than ~3 sources changed, draft with one sub-agent per source folder
   in parallel, then deduplicate.
4. Review with me item by item (approve / edit / reject). Never bulk-accept
   Pricing_Rules or Central_Reference — always show me the full diff for those.
5. Apply accepted edits in place on branch refresh/YYYY-MM-DD-<topic>. Never
   create, rename or delete brain files (each is wired to an n8n tool by name).
   Commit, push, open a PR with: Summary / Files updated (bullets per file) / Sources.
6. Independent review: start a SEPARATE agent that did not draft the changes,
   read-only, that reads the PR diff and the cited sources and answers:
   is every edit supported by its source? any new contradiction elsewhere in the
   repo? what was missed? anything net-negative? would a prospect get better
   answers after merging? Relay its findings; fix real issues on the same branch.
7. Stop. I review and merge on GitHub myself.
8. After I confirm the merge: pull main, then write the new hashes to
   state/manifest.json (only now — if the PR is abandoned, the same drift must
   come back next run). Never commit state/ to the repo; it is public.
```

### Optional: schedule it

When the scrapers and drift detection run reliably by hand, you can schedule the scrapers plus the *drift detection and proposal drafting* (steps 1–3 of Prompt 5) weekly, using cron, launchd, a GitHub Action or similar. Have the scheduled run write a proposal file for you to review, and keep review, PR and merge interactive. The bot answers customers by itself, so a human should approve every change to what it knows.
