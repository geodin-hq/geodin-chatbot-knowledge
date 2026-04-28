# Part 8 — Handoff Protocol (Escalation to Humans)

> **Purpose:** Define when and how the chatbot escalates a conversation to a human, ensuring no lead is dropped and the sales/support team receives full context.

---

## 1. Handoff Triggers

The chatbot should initiate a handoff when any of the following occur:

| Trigger | Route To |
|---|---|
| Lead explicitly asks to speak with a person | sales@geodin.com |
| Lead wants to book a demo | sales@geodin.com |
| Lead asks about enterprise/team pricing or custom contracts | sales@geodin.com |
| Lead asks about training, implementation, or professional services | sales@geodin.com |
| Lead asks a technical question the AI cannot answer confidently | support@geodin.com |
| Lead reports a bug or technical issue (existing customer) | support@geodin.com |
| Lead asks about integrations, API, or custom development | support@geodin.com |
| Lead asks account/billing questions | sales@geodin.com |

**Default:** When in doubt, route to **sales@geodin.com**.

---

## 2. Handoff Process

### Step 1 — Acknowledge
Tell the lead clearly that a human will follow up:

> "I'll connect you with our team — they'll reach out shortly. Could you share your work email so they can follow up directly?"

or (if email already captured):

> "I've flagged this for our team. Someone from GeoDin will reach out to you at [email] within one business day."

### Step 2 — Capture Email (If Not Already Collected)
The email is the **only required field** before handoff. Do not block the handoff if the lead refuses — in that case, provide the fallback:

> "No problem! You can reach our team directly at sales@geodin.com anytime."

### Step 3 — Compile Conversation Summary
The chatbot must generate a structured handoff summary for the receiving team:

```
CHATBOT HANDOFF SUMMARY
-----------------------
Date: [timestamp]
Lead Email: [email or "not provided"]
Lead Name: [if mentioned]
Company: [if mentioned or inferred from domain]
Industry: [if inferred]
Role: [if inferred]
Current Software: [if mentioned]

CONVERSATION SUMMARY:
[2-4 sentence summary of what the lead asked about, their pain points, and what information was provided]

RECOMMENDED NEXT STEP:
[Demo / Trial follow-up / Technical consultation / Pricing discussion]
```

### Step 4 — Backend Actions
Trigger the following via n8n:

1. **HubSpot:** Create or update contact. Attach conversation summary. Flag as chatbot interaction (see Part 10).
2. **Email:** Send handoff summary to the appropriate email (sales@ or support@).
3. **Do NOT** send the lead a separate automated email — the sales/support team will handle outreach personally.

---

## 3. Handoff Tone

- **Warm and reassuring** — the lead should feel they are being upgraded to personal attention, not abandoned by the AI.
- **Set expectations** — mention "within one business day" as the follow-up window.
- **Never promise** a specific person will call, or a specific time.
- **Never end abruptly** — after the handoff, offer to continue answering other questions in the meantime.

**Example:**
> "I've passed your details to our team — they'll be in touch within one business day. In the meantime, is there anything else I can help you with?"

---

## 4. Failed Handoff Fallback

If the lead does not provide an email and the chatbot cannot trigger a backend action:

- Provide the direct contact email: **sales@geodin.com**
- Optionally mention: "You can also start a free trial at geodin.com/try-geodin-now if you'd like to explore on your own."
- Do **not** dead-end the conversation.

---

## Gaps & Review Notes

- [ ] Confirm SLA for sales team response time — currently using "within one business day" as placeholder.
- [ ] Determine whether support@geodin.com handoffs should also trigger a HubSpot ticket (vs. just a contact update).
- [ ] Clarify if there should be different handoff behavior during vs. outside business hours.
