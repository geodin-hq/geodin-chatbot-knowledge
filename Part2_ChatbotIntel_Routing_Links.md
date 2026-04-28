# Part 6 — Routing Links & Funnel Navigation

> **Purpose:** Define the exact URLs, email addresses, and actions the chatbot uses to route visitors at each stage of the funnel.

---

## 1. Primary Routing Table

| Intent | Action | Destination |
|---|---|---|
| **Start a free trial** | Link to trial page | https://www.geodin.com/try-geodin-now |
| **Try GeoDin Ground** | Link to Autodesk App Store | https://apps.autodesk.com/CIV3D/en/Detail/Index?id=7392344363451764169&appLang=en&os=Win64 |
| **See pricing** | Link to pricing page | https://www.geodin.com/pricing |
| **Book a demo** | Capture email, trigger sales handoff | Chatbot says: "Our sales team will reach out to book a demo." Trigger → sales@geodin.com + HubSpot |
| **General sales inquiry** | Capture email, trigger sales handoff | sales@geodin.com + HubSpot |
| **Technical documentation** | Link to docs site | https://docs.geodin.com |
| **Help / support (existing customer)** | Email to docs team | docs@geodin.com |
| **Complex technical question** | Email to support team | support@geodin.com |
| **Speak to a human** | Handoff to sales | sales@geodin.com + HubSpot (see Part 8 — Handoff Protocol) |
| **GeoDin homepage** | Link | https://www.geodin.com |

---

## 2. Demo Booking Flow (No External Calendar Link)

GeoDin does **not** use a self-service calendar booking tool. The chatbot must **not** provide a booking URL.

**Instead, the demo booking flow is:**

1. Lead expresses interest in a demo.
2. Chatbot captures their corporate email (minimum required field).
3. Chatbot confirms: "Thanks! Our sales team will reach out to you shortly to schedule a personalized demo."
4. Backend triggers:
   - Create/update HubSpot contact with chatbot interaction flag.
   - Submit conversation summary to HubSpot (form submission or contact property update).
   - Email notification to sales@geodin.com with lead details and conversation context.

**Example response:**
> "I'd love to set that up for you! Could you share your work email? Our sales team will reach out within one business day to find a time that works."

---

## 3. Free Trial Flow

1. Lead expresses interest in trying GeoDin.
2. Chatbot determines which product:
   - **GeoDin Core / Onsite** → https://www.geodin.com/try-geodin-now
   - **GeoDin Ground (Civil 3D plugin)** → https://apps.autodesk.com/CIV3D/en/Detail/Index?id=7392344363451764169&appLang=en&os=Win64
3. Chatbot provides the link and offers to answer any questions about getting started.

**Example response:**
> "You can start a free 14-day trial right here: geodin.com/try-geodin-now — no credit card required. Want me to walk you through what you'll see when you log in?"

---

## 4. Support Routing (Existing Customers)

If the visitor identifies as an existing GeoDin customer:

| Need | Route |
|---|---|
| General help, how-to questions | docs@geodin.com |
| Technical issue or bug report | support@geodin.com |
| Documentation / self-service | https://docs.geodin.com |
| Account or billing questions | sales@geodin.com |

**The chatbot should first attempt to answer from its knowledge base.** Only route to email when the question exceeds its knowledge or the customer explicitly requests human help.

---

## 5. Routing Rules

- **Never fabricate a URL.** Only use the links listed in this document.
- **Never provide a direct calendar booking link** — GeoDin uses manual scheduling via the sales team.
- **Always capture email before triggering a handoff.** The sales team needs a way to follow up.
- **If unsure where to route**, default to sales@geodin.com.

---

## Gaps & Review Notes

- [ ] Confirm whether a Calendly or HubSpot meeting link will be set up in the future — if so, update the demo booking flow.
- [ ] Verify the GeoDin Ground Autodesk App Store link is still current.
- [ ] Determine if the chatbot should also link to the GeoDin blog or resources page for top-of-funnel visitors.
