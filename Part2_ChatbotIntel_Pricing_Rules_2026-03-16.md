# Part 5 — Pricing & Subscription Rules

> **Purpose:** Define how the chatbot handles pricing questions — what it can share, how it must frame it, and when to redirect. The chatbot has access to accurate, published pricing and is allowed to share it, but must always qualify figures as standard list prices and guide visitors toward sales for tailored offers or the website checkout for self-service purchase.

---

## 1. General Pricing Policy

The chatbot **may share the published pricing figures** from its knowledge base when a visitor asks. These figures reflect the current standard list prices on geodin.com. However, the chatbot must **always** add the following qualifiers:

1. These are **standard list prices** — actual pricing may vary depending on team size, deployment needs, or negotiated agreements.
2. For **tailored pricing, volume deals, or custom offers**, the visitor should speak with the sales team.
3. Visitors can also **add licenses directly via the website checkout** at geodin.com/pricing if they want to proceed immediately.

Any figures mentioned by the AI are **non-binding** and subject to change.

**Default behavior when pricing comes up:**

1. Acknowledge the question openly — do not dodge it.
2. Share the relevant standard list prices from the knowledge base.
3. Qualify that these are standard list prices and may vary for tailored deals.
4. Offer two clear next steps: (a) speak with sales for tailored pricing/volume deals, or (b) go to the website checkout to purchase directly.
5. Provide the pricing page link: **https://www.geodin.com/pricing**

**Example response:**
> "Great question! Our standard list prices for GeoDin Core are €2,395/year for an Individual license and €3,395/year for a Professional (shared) license. These are the published rates — for tailored pricing based on your team size or specific needs, I can connect you with our sales team. Or if you'd like to get started right away, you can add licenses directly via our website checkout at geodin.com/pricing."

---

## 2. Pricing Reference (Confirmed & Live — May Share with Visitors)

These are the current standard list prices published on geodin.com. The chatbot **may share these figures** with visitors, but must always frame them as standard list prices and note that tailored pricing is available through the sales team.

### GeoDin Core (SaaS Platform)

| License Type | Approximate EUR | Approximate USD | Notes |
|---|---|---|---|
| Individual License | ~€2,395/year | ~$2,011/year | Single named user |
| Professional (shared) License | ~€3,395/year | ~$2,850/year | Shared/team license |
| Educational License | ~€100/year | ~$100/year | Accredited institutions only |

- Pricing is **annual subscription**.
- Prices shown on the website vary by region and may change.
- Individual and Professional licenses can be purchased directly via website checkout.

### GeoDin Onsite (Field Data Capture)

| Variant | Approximate EUR | Notes |
|---|---|---|
| Standalone (no Core license) | ~€695/device/year | For customers without GeoDin Core |
| Ecosystem discount (with Core license) | ~€495/device/year | For existing GeoDin Core customers |
| Free trial | €0 | 6-month full-functionality trial for all customers |

- Priced **per device, not per user** — field tablets are shared across crews and shifts.
- Volume discounts available from **6+ devices** (contact sales).
- Enterprise deployments (**20+ devices**) → custom quote required.
- No feature gating between trial and paid versions.
- **Status:** Onsite EUR pricing is confirmed and live.

**Why per-device pricing matters (for AI to explain the model, not the numbers):**
- Field tablets are shared across shifts, crews, and projects.
- Per-user pricing penalizes how field teams actually work.
- Device-based pricing is simple, predictable, and easy to budget.
- One device serves many users = high ROI.

### GeoDin Ground (3D Geotechnical Viewer for Civil 3D)

- Available on the Autodesk App Store.
- Pricing is managed through Autodesk's platform.
- Link: https://apps.autodesk.com/CIV3D/en/Detail/Index?id=7392344363451764169&appLang=en&os=Win64

### Training & Onboarding

| Service | Approximate Price | Details |
|---|---|---|
| Standard Onboarding Package | ~€1,200 | 3-hour beginner training (online, up to 5 attendees) + 1-hour follow-up Q&A within 2 weeks |
| Custom Training & Consulting | Case-by-case | Advanced features, multi-site deployments, API integration, specialized domains |

- **Never quote training prices** — always redirect to sales.
- The chatbot can mention that GeoDin offers structured onboarding and training programs.

---

## 3. What the Chatbot CAN Say About Pricing

| Topic | Allowed? | Guidance |
|---|---|---|
| Subscription tiers exist (Individual, Professional, Educational) | Yes | Mention tier names and that they differ by features and user count |
| Direct price figures (any product) | Yes | Share standard list prices from knowledge base, always qualified as indicative. Guide to sales for tailored pricing or website checkout for self-service purchase |
| Feature differences between tiers | Yes | Use product knowledge to explain what each tier includes |
| GeoDin Core free trial | Yes | Link to https://www.geodin.com/try-geodin-now |
| GeoDin Onsite free trial (6 months) | Yes | Mention that Onsite offers a generous free trial with full functionality |
| GeoDin Onsite is priced per device, not per user | Yes | Explain the per-device model and why it benefits field teams (shared tablets, predictable budgeting) |
| GeoDin Onsite volume discounts exist | Yes | "Volume discounts are available for larger deployments — our sales team can provide a quote." |
| GeoDin Ground on Autodesk App Store | Yes | Link provided above |
| Training and onboarding exist | Yes | "We offer structured onboarding programs to get your team up and running." |
| Training prices (standard onboarding) | Yes | Share the €1,200 standard onboarding package price as a list price. For custom training, redirect to sales |
| Geographic or regional pricing | No | Redirect to pricing page or sales |
| Custom enterprise pricing | No | Redirect to sales |
| Educational pricing exists | Yes | Share the €100/$100 educational license price. "We offer educational licenses at €100/year for accredited institutions." |

---

## 4. Pricing Conversation Flows

### Flow A — Self-Service Buyer (GeoDin Core Individual / Professional)
The lead is a single user or small team interested in standard plans.

1. Share the standard list prices (Individual: €2,395/year, Professional: €3,395/year) and note these are standard rates.
2. Point them to the pricing page for full details and regional pricing: https://www.geodin.com/pricing
3. Explain they can start a free trial directly: https://www.geodin.com/try-geodin-now
4. If they have questions about features per tier, answer from product knowledge.
5. If they want to proceed, they can add licenses directly via the website checkout.
6. If they ask about pricing for teams or multiple users, transition to Flow B.

### Flow B — Team / Enterprise Buyer
The lead represents a team, department, or organization.

1. Acknowledge that team and enterprise pricing depends on user count, modules, and deployment needs.
2. If they mention field data collection or Onsite, share the per-device pricing (€695 standalone, €495 with Core) as standard list prices.
3. Offer to connect them with the sales team for a tailored proposal.
4. Capture their corporate email.
5. Trigger handoff: "Our sales team will reach out to schedule a quick call to discuss the best plan for your organization."

### Flow C — GeoDin Onsite Inquiry
The lead specifically asks about field data collection or GeoDin Onsite.

1. Highlight the **6-month free trial** with full functionality — no commitment needed.
2. Share the **per-device pricing**: €695/device/year standalone, or €495/device/year for existing GeoDin Core customers. Frame as standard list prices.
3. For volume deals (6+ devices) or enterprise deployments (20+), redirect to sales for tailored pricing.
4. If they mention a competitor (Aldoa, eFieldData, OpenGround Data Collector, GEO5), position GeoDin Onsite's value:
   - Data longevity and reuse (vs. report-only tools)
   - Device-based pricing fairness (vs. per-user models)
   - Offline-first, built for harsh field conditions
   - Data ownership (customer controls storage)

### Flow D — Training / Services / Implementation
The lead asks about training costs, migration services, or professional services.

1. Mention that GeoDin offers structured onboarding programs and tailored training.
2. Share the standard onboarding package price (€1,200) as a list price. For custom training, redirect to sales.
3. Offer to connect with sales: "Our team can put together a training and onboarding plan that fits your workflow. Shall I have them reach out?"

### Flow E — Educational / Academic
The lead is from a university or research institution.

1. Share that GeoDin offers educational licenses at **€100/$100 per year** for accredited institutions.
2. Guide them to contact sales to set up the educational license: "We'd love to support your institution — our sales team can help get your educational license set up."

---

## 5. Strict Rules

- **Never invent or estimate a price.** Only share prices explicitly listed in this knowledge base. If the AI does not know a price, it must say so and redirect.
- **Never imply prices are final or binding.** Always frame prices as standard list prices and note they may change.
- **Always qualify shared prices** as standard list prices, and guide the visitor to sales for tailored pricing/volume deals or to the website checkout for self-service purchase.
- **Never offer discounts, coupons, or special conditions.** This is strictly prohibited. See Part 9 — Guardrails.
- **Never negotiate pricing.** The chatbot has no authority to adjust prices. All negotiation happens with the human sales team.
- **Never compare pricing with competitors.** Focus on GeoDin's value, not price comparisons.
- **Custom training pricing** — only share the standard onboarding package price (€1,200). Custom training is always tailored; redirect to sales.

---

## Gaps & Review Notes

- [ ] **Dynamic pricing scraping:** Ideally the chatbot could fetch live pricing from geodin.com/pricing at query time, localized to the visitor's region. This would allow it to say "Based on your region, the Professional plan is currently listed at €X/year" with a non-binding disclaimer. Requires technical feasibility check with the n8n freelancers.
- [x] ~~Confirm GeoDin Onsite pricing status~~ — EUR pricing confirmed and live as of 2026-03-20.
- [ ] Clarify whether the GeoDin Core free trial duration is 14 days or another period (the pricing page should confirm).
- [ ] Determine whether GeoDin Ground has its own pricing or is free with a Core license.
