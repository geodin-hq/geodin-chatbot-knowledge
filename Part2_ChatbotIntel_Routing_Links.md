# Part 6 — Routing Links & Funnel Navigation

> **Purpose:** Define the exact URLs, email addresses, and actions the chatbot uses to route visitors at each stage of the funnel.

---

## 1. Primary Routing Table

| Intent | Action | Destination |
|---|---|---|
| **Start a free trial** | Link to trial page | https://www.geodin.com/try-geodin-now |
| **Try GeoDin Ground** | Link to Autodesk Marketplace listing (canonical; old App Store URL points to the same app) | https://marketplace.autodesk.com/apps/e980e6d6-57f3-4de3-b311-0da8181b0ff6 |
| **See pricing** | Link to pricing page | https://www.geodin.com/pricing |
| **Book a demo** | Capture email, trigger sales handoff | Chatbot says: "Our sales team will reach out to book a demo." Trigger → sales@geodin.com + HubSpot |
| **General sales inquiry** | Capture email, trigger sales handoff | sales@geodin.com + HubSpot |
| **Technical documentation** | Link to docs site | https://docs.geodin.com |
| **Help / support (existing customer, EU/global)** | Email to docs team | docs@geodin.com |
| **Help / support (existing customer, North America)** | Route to Symetri (authorized N.A. partner) | https://www.symetri.us · 800.336.3375 |
| **Complex technical question** | Support portal (preferred — trackable tickets) or email | https://support.geodin.com · support@geodin.com |
| **GeoDin Ground release notes / "what's new"** | Link to docs release notes | https://docs.geodin.com/geodin-ground/support/release-notes |
| **Speak to a human** | Handoff to sales | sales@geodin.com + HubSpot (see Part 8 — Handoff Protocol) |
| **GeoDin vs gINT comparison / gINT migration** | Link to alternative-for page | https://www.geodin.com/alternative-for/gint |
| **gINT discontinuation thought-leadership** | Link to GeoDin's geoengineer.org article ("Life after gINT — Rethinking geotechnical data management for a new era", March 2026) | https://www.geoengineer.org/news/life-after-gint-rethinking-geotechnical-data-management-for-a-new-era |
| **Subsurface data / digital transformation thought-leadership** | Link to GeoDin-authored article on Autodesk's blog ("The Ground Beneath Digital Transformation", May 2026) | https://www.autodesk.com/blogs/construction/the-ground-beneath-digital-transformation-subsurface-data-is-the-next-frontier/ |
| **Proof of Autodesk ecosystem recognition** | Link to Autodesk's own guide featuring GeoDin as a top infrastructure integration (April 2026) | https://www.autodesk.com/blogs/construction/your-guide-to-the-top-autodesk-integrations-for-infrastructure-projects/ |
| **GeoDin vs OpenGround comparison** | Link to alternative-for page | https://www.geodin.com/alternative-for/openground |
| **GeoDin vs BoreDM comparison** | Link to alternative-for page | https://www.geodin.com/alternative-for/boredm |
| **GeoDin Ground vs Geotechnical Modeler** | Link to alternative-for page | https://www.geodin.com/alternative-for/geotechnical-modeler |
| **Autodesk geotechnical solutions page (evergreen partnership proof point)** | Link to Autodesk's permanent solutions page featuring GeoDin Ground | https://www.autodesk.com/solutions/geotechnical-engineering |
| **ArcGIS / Esri integration questions** | Link to the Esri ArcGIS integration page | https://www.geodin.com/integrations/esri-arcgis |
| **AGS data management feature deep-link** | Link to feature page | https://www.geodin.com/features/ags-data-management |
| **GeoDin homepage** | Link | https://www.geodin.com |
| **Book / ask about training** | Link to training page (pricing still via sales) | https://www.geodin.com/book-a-training |
| **What's new / latest release** | Link to release notes page | https://www.geodin.com/release-notes |
| **News, blogs, case studies** | Link to newsroom | https://www.geodin.com/newsroom |
| **Office locations / visit us** | Link to locations page | https://www.geodin.com/locations |
| **Industry fit — infrastructure** | Link to industry page | https://www.geodin.com/industries/infrastructure-projects |
| **Industry fit — environmental monitoring** | Link to industry page | https://www.geodin.com/industries/environmental-monitoring |
| **Industry fit — land reclamation** | Link to industry page | https://www.geodin.com/industries/land-reclamation |
| **Industry fit — tunnel monitoring** | Link to industry page | https://www.geodin.com/industries/tunnel-monitoring |
| **Alternatives overview (gINT / OpenGround / BoreDM)** | Link to alternatives hub | https://www.geodin.com/alternative-for |

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
   - **GeoDin Ground (Civil 3D plugin)** → https://marketplace.autodesk.com/apps/e980e6d6-57f3-4de3-b311-0da8181b0ff6
3. Chatbot provides the link and offers to answer any questions about getting started.

**Example response:**
> "You can start a free 30-day trial right here: geodin.com/try-geodin-now — no credit card required. Want me to walk you through what you'll see when you log in?"

---

## 4. Support Routing (Existing Customers)

If the visitor identifies as an existing GeoDin customer, route by region:

### EU / Global

| Need | Route |
|---|---|
| General help, how-to questions | docs@geodin.com |
| Technical issue or bug report | support@geodin.com |
| Documentation / self-service | https://docs.geodin.com |
| Account or billing questions | sales@geodin.com |

### North America (US & Canada) — Symetri

GeoDin's authorized North American partner is **Symetri** (Autodesk Platinum Partner, 1,000+ employees). North American customers can access dedicated technical support, official GeoDin training, and customization through Symetri.

| Need | Route |
|---|---|
| US/Canada technical support | https://www.symetri.us · 800.336.3375 |
| Official GeoDin training (N.A.) | Symetri (delivers locally on GeoDin's behalf) |
| Customization & add-ins (N.A.) | Symetri |
| Documentation / self-service | https://docs.geodin.com |
| Sales / commercial discussion | sales@geodin.com (or via Symetri's local team) |

**The chatbot should first attempt to answer from its knowledge base.** Only route to email/partner when the question exceeds its knowledge or the customer explicitly requests human help.

**Example for a US support question:**
> "For dedicated US support, our authorized North American partner Symetri handles GeoDin support tickets. You can reach them at symetri.us or 800.336.3375. Want me to also flag this internally so the GeoDin Berlin team is aware?"

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
