# Part 10 — Ecosystem Integration (n8n + HubSpot)

> **Purpose:** Define how the chatbot connects to HubSpot CRM and other systems, what data flows where, and how the sales team gets notified.

---

## 1. Architecture Overview

```
Visitor ↔ Website Chatbot (AI)
              ↓
         n8n Workflow
              ↓
     ┌────────┴────────┐
     ↓                 ↓
  HubSpot CRM     Email (SMTP)
     ↓
  HubSpot Workflows
     ↓
  Microsoft Teams Notification
```

---

## 2. HubSpot Integration — Two Recommended Approaches

### Option A: Form Submission (Recommended)

Create a **HubSpot form** dedicated to chatbot leads. The n8n workflow submits this form programmatically with the data collected during the conversation.

**Why form submission is preferred:**
- Form submissions are treated with **high urgency** in HubSpot — they trigger immediate workflows and appear in the activity timeline.
- Unstructured conversation context can be passed in a free-text field, preserving nuance that structured fields would lose.
- HubSpot's existing lead processing workflows (notifications, assignment, scoring) can be reused.

**Suggested form name:** `Chatbot_Lead_Capture`

**Suggested form fields:**

| Field | Type | Required | Source |
|---|---|---|---|
| Email | Email | Yes | Explicitly captured from lead |
| First Name | Text | No | If mentioned in conversation |
| Last Name | Text | No | If mentioned in conversation |
| Company | Text | No | Inferred from email domain or conversation |
| Industry | Dropdown | No | Inferred from conversation (geotech, civil, construction, government, mining, environmental, lab, other) |
| Role / Job Title | Text | No | If mentioned or inferred |
| Current Software | Text | No | If mentioned (e.g., gINT, OpenGround, Excel) |
| Conversation Summary | Multi-line text | Yes | AI-generated summary of the conversation |
| Chatbot Intent | Dropdown | No | Demo request / Trial interest / Pricing question / Technical question / General inquiry |
| Lead Source Detail | Hidden | Yes | Auto-filled: "Website Chatbot" |

### Option B: Direct Contact Creation via API

Use the HubSpot Contacts API to create or update a contact directly, then attach a note with the conversation summary.

**When to use this instead:**
- If form submission causes duplicate handling issues.
- If the freelancers prefer API-level control.

**In either case, the following must happen:**
1. Contact is created or updated (deduplicate by email).
2. Conversation summary is attached as a note or in a form field.
3. The contact is flagged as a chatbot interaction (see Section 3).

---

## 3. Chatbot Interaction Tracking

**Create a custom HubSpot contact property:**

| Property | Details |
|---|---|
| **Internal name** | `n8n_chatbot` |
| **Label** | "N8N Chatbot Interaction" |
| **Type** | Single checkbox (Yes/No) or Date (timestamp of last interaction) |
| **Group** | Contact information |

**Purpose:** Allows the sales team and HubSpot workflows to:
- Filter contacts who came through the chatbot.
- Build lists and reports on chatbot-sourced leads.
- Trigger chatbot-specific follow-up sequences.

**Additional suggested properties:**

| Property | Type | Purpose |
|---|---|---|
| `chatbot_intent` | Dropdown | What the lead was looking for (Demo / Trial / Pricing / Technical / General) |
| `chatbot_conversation_summary` | Multi-line text | Full AI-generated conversation summary |
| `chatbot_last_interaction_date` | Date | Timestamp of last chatbot conversation |

---

## 4. Notification Flow

Notifications are handled **downstream in HubSpot**, not by the chatbot or n8n directly.

**Current setup:**
1. Chatbot conversation → n8n → HubSpot (form submission or contact creation).
2. HubSpot workflow triggers on new form submission or contact property change.
3. Workflow sends email notification with lead details.
4. Existing rules forward to **Microsoft Teams** channel for sales team visibility.

**The chatbot/n8n side only needs to ensure the data lands in HubSpot correctly.** All routing, assignment, and notification logic lives in HubSpot workflows.

---

## 5. Data Passed to HubSpot — Summary

Every chatbot interaction that captures an email should send:

```json
{
  "email": "lead@company.com",
  "firstname": "Maria",
  "lastname": "Santos",
  "company": "GeoTech Solutions",
  "n8n_chatbot": true,
  "chatbot_intent": "Demo request",
  "chatbot_conversation_summary": "Lead is a project manager at a geotech consultancy with 50+ engineers. Currently using gINT but frustrated with field data collection workflow. Interested in GeoDin Core + Onsite. Wants a demo focused on data migration from gINT.",
  "chatbot_last_interaction_date": "2026-03-16T14:30:00Z"
}
```

---

## 6. Edge Cases

| Scenario | Behavior |
|---|---|
| Lead does not provide email | No HubSpot submission. Chatbot provides sales@geodin.com as fallback. |
| Lead returns for a second conversation | Update existing contact (deduplicate by email). Append new conversation summary. |
| Lead is disqualified (vendor, job seeker) | Do **not** create a HubSpot contact. No form submission. |
| Conversation has no commercial intent | Optional: create contact with intent = "General inquiry" and low priority. Or skip submission entirely. |

---

## 7. Technical Notes for n8n Freelancers

- **HubSpot API:** Use the HubSpot CRM API v3 for contact creation and form submission.
- **Deduplication:** Always search for existing contacts by email before creating new ones.
- **Rate limits:** HubSpot API has rate limits (100 requests per 10 seconds for most endpoints). Chatbot volume should be well within this.
- **Form submission endpoint:** `POST https://api.hsforms.com/submissions/v3/integration/submit/{portalId}/{formGuid}`
- **Error handling:** If HubSpot submission fails, log the error and still send the email to sales@geodin.com as a fallback.

---

## Gaps & Review Notes

- [ ] **HubSpot portal ID and form GUID** need to be configured once the form is created.
- [ ] Confirm the custom property internal name (`n8n_chatbot`) with the team — Nuno mentioned potentially naming it "NA10 chatbot."
- [ ] Decide: Should the conversation transcript (full chat log) also be stored in HubSpot, or only the AI-generated summary?
- [ ] Clarify: Should disqualified visitors (vendors, job seekers) be tracked at all for analytics purposes?
- [ ] Test: Confirm that HubSpot form submissions trigger existing notification workflows as expected.
- [ ] Discuss with freelancers: Webhook vs. polling approach for n8n → HubSpot integration.
