# GeoDin Chatbot Knowledge Base — Index

> Knowledge base for the GeoDin website AI chatbot (n8n).
> Last updated: 2026-03-20

---

## Structure

The knowledge base is organized into two parts:

- **Part 1 — Knowledge Base:** Core product and company knowledge the chatbot draws from to answer visitor questions.
- **Part 2 — Chatbot Intelligence:** Operational rules, guardrails, and conversation logic that shape how the chatbot behaves.

### Naming Convention

```
Part[X]_[Category]_[Topic]_[YYYY-MM-DD].md
```

---

## Part 1 — Knowledge Base

| File | Description |
|------|-------------|
| `Part1_KnowledgeBase_ValueProposition_Personas` | GeoDin's core value proposition, the problem it solves, and 8 target personas (Geotechnical Consultant, Project Manager, IT/Data Manager, Lab Manager, Civil Engineer, Environmental Consultant, Field Operator, GIS Specialist) with persona-specific pain points and how GeoDin addresses them. |
| `Part1_KnowledgeBase_ProductSuite` | Detailed overview of the three GeoDin products (Core, Onsite, Ground), how they work together as an end-to-end suite, technical specs (deployment, databases, standards, integrations), and verified pricing. |
| `Part1_KnowledgeBase_Credibility_Trust` | Company history, scale metrics (projects, countries), named clients (Arcadis, Fugro Brasil, German government), strategic partnerships (Autodesk Gold, Symetri, AGS), major reference projects, data sovereignty, and support model. |
| `Part1_KnowledgeBase_CompetitivePositioning` | Structured competitive analysis for 7 competitors: OpenGround, gINT, BoreDM, Geotechnical Modeler (retired), Aldoa, eFieldData, GEO5 Data Collector. Each with: what they offer, where GeoDin wins, honest trade-offs, switching personas, and migration talking points. Includes a 7-competitor comparison table and chatbot conversation principles. |

## Part 2 — Chatbot Intelligence

| File | Description |
|------|-------------|
| `Part2_ChatbotIntel_TechnicalQA` | Technical Q&A pairs the chatbot can use to answer product, deployment, and integration questions. |
| `Part2_ChatbotIntel_CommercialQA` | Commercial Q&A covering pricing, licensing, trials, onboarding, and purchasing questions. |
| `Part2_ChatbotIntel_Pricing_Rules` | Rules for how the chatbot should handle pricing conversations, what to disclose, and when to route to sales. |
| `Part2_ChatbotIntel_Qualification_Rules` | Lead qualification logic — how the chatbot identifies visitor intent and scores leads. |
| `Part2_ChatbotIntel_Guardrails` | Boundaries and safety rules: what the chatbot should and should not say, competitor handling, legal constraints. |
| `Part2_ChatbotIntel_Ecosystem_Integration` | How GeoDin fits into the broader AEC technology ecosystem (Autodesk, Esri, Leapfrog, etc.). |
| `Part2_ChatbotIntel_Handoff_Protocol` | When and how the chatbot should hand off to a human (sales, support, or consulting). |
| `Part2_ChatbotIntel_Routing_Links` | URLs, CTAs, and routing destinations the chatbot can direct visitors to. |
| `Part2_ChatbotIntel_ToneOfVoice` | Chatbot persona (Technical Sales Rep), tone of voice (sharp, challenger, respected), language patterns, words to avoid, tone adaptation per language and conversation stage. |

---

## Gaps & Review Notes

Every knowledge base file (Part 1) ends with a **"Gaps & Review Notes"** section. These flag:

- Information the AI was unsure about or couldn't verify
- Data points that need confirmation from the GeoDin team (e.g., exact founding year, project counts)
- Areas where the source material was thin (e.g., BoreDM competitive intel)
- Gaps that have been resolved (marked with ~~strikethrough~~ and **RESOLVED**)

The project team should review these gaps periodically and update the files as new information becomes available.
