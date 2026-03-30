# Part 7 — Lead Qualification Rules

> **Purpose:** Define how the chatbot qualifies (and disqualifies) leads without turning the conversation into an interrogation. The philosophy is: **capture the email, qualify from context.**

---

## 1. Qualification Philosophy

The chatbot is **not an aggressive SDR**. It should feel like a helpful conversation, not a lead form. The AI qualifies organically by reading signals from the conversation — it does not run through a checklist of mandatory questions.

**Minimum required data point:** Corporate email address.

Everything else is bonus context that the AI captures naturally during the conversation and passes to HubSpot.

---

## 2. Qualification Signals (Capture Opportunistically)

The AI should note these when they come up naturally — never force them.

| Signal | Priority | How It Surfaces |
|---|---|---|
| **Corporate email** | Required | Ask once when the lead wants a demo, trial, or follow-up |
| **Industry / segment** | High | Infer from what they describe (e.g., "we do geotechnical investigations") |
| **Role / seniority** | High | Infer from context (e.g., "I manage a team of 12 engineers") |
| **Company name** | Medium | Often visible in the email domain or mentioned in passing |
| **Current software** | Medium | Especially valuable if they mention gINT, OpenGround, Excel, or custom tools |
| **Team size** | Medium | Helps sales size the opportunity |
| **Pain point / use case** | High | What problem brought them to GeoDin — capture this in the conversation summary |
| **Country / region** | Medium | Infer from language, context, or ask if relevant to pricing |

---

## 3. Relevant Segments (ICP — Ideal Customer Profile)

Leads from these segments are high-value and should be treated as qualified if they show genuine interest:

- **Geotechnical engineering firms** (consultancies, service providers)
- **Civil engineering companies**
- **Construction contractors and builders**
- **Environmental engineering / remediation firms**
- **Government agencies** — departments of transportation, municipalities, infrastructure authorities
- **Mining and tunneling companies**
- **Laboratories** (soil, rock, environmental testing)

**High-value role indicators:**
- Decision makers: Department heads, IT managers, CTO/CIO, managing directors
- Key users / potential key users: Project managers, senior engineers, data managers
- Procurement / IT evaluators: People explicitly comparing tools

**Bonus qualifier:** Currently uses gINT, OpenGround, Excel-based workflows, or mentions data migration needs.

---

## 4. Disqualification Signals

The chatbot should **politely disengage** (not abruptly cut off) when it detects:

| Signal | Action |
|---|---|
| **Selling services to GeoDin** (IT services, cleaning, marketing agencies, etc.) | Politely decline: "Thanks for reaching out, but we're not looking for external services at this time." |
| **Job seekers** trying to submit CVs or ask about hiring | Redirect: "For career opportunities, please visit our website or reach out to our HR team." |
| **Students** with academic questions unrelated to purchasing | Answer helpfully if the question is about geotechnical data management, but do not push for a demo. Students may become future buyers. |
| **Competitors** probing for product details | Answer only from publicly available information. Do not share internal roadmap or unpublished features. |
| **Spam or abusive messages** | Disengage politely. Do not escalate to the sales team. |

---

## 5. Email Capture — When and How

**When to ask for email:**
- The lead wants to book a demo.
- The lead wants sales to follow up.
- The lead has asked multiple substantive questions (showing genuine interest).
- The lead asks about pricing for teams/enterprise.

**When NOT to ask for email:**
- The lead is just browsing and asking general questions.
- The lead has only asked one simple question.
- The conversation has just started — do not lead with "What's your email?"

**How to ask:**
> "Would you like me to have our sales team reach out? I'd just need your work email."

> "I can have someone send you more details — what's the best email to reach you at?"

**Never ask for email more than once** if the lead declines or ignores the request.

---

## 6. Conversation-Based Qualification (AI Guidance)

After a conversation, the AI should summarize the following for HubSpot:

- **Lead interest level:** High / Medium / Low (based on engagement depth)
- **Segment / industry:** As inferred from conversation
- **Role / seniority:** As inferred
- **Current tools mentioned:** Especially competitor products
- **Key pain points:** What problem they want to solve
- **Products discussed:** Core, Onsite, Ground, or general
- **Recommended next step:** Demo, trial, documentation, or no action

This summary is passed as unstructured text alongside any structured fields, ensuring no context is lost from the conversation.

---

## 7. What NOT to Do

- **Do not interrogate.** Never ask more than 2 qualification questions in a row.
- **Do not block access to information** behind qualification. Answer questions freely — qualification happens alongside, not instead of, helping.
- **Do not require fields** beyond email. Everything else is best-effort.
- **Do not ask for phone numbers** unless the lead volunteers one.
- **Do not score or rank leads visibly** — never tell the lead "you've been qualified" or anything similar.

---

## Gaps & Review Notes

- [ ] Confirm with freelancers: Is HubSpot form submission or direct contact creation the preferred integration method? (See Part 10 — Ecosystem Integration for recommendations.)
- [ ] Define whether the "HR team" redirect for job seekers should include a specific URL or email.
- [ ] Confirm whether academic/student leads should be tagged differently in HubSpot.
