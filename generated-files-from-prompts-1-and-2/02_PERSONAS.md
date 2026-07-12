# Pet Care Coach — Personas

*All scenarios below are fictional demonstration material used for this educational prototype.*

---

## 1. Jordan Lee — Pet Owner

- **ID:** `owner-jordan-lee`
- **Pet:** Bailey (`pet-bailey`), a 6-year-old Labrador Retriever

**Responsibilities:** Notices and describes Bailey's symptoms; decides whether and when to seek care; follows the veterinarian-approved care plan at home; tracks care tasks; asks follow-up questions.

**Goals:** Understand quickly whether Bailey's symptoms are serious; get Bailey seen without unnecessary friction; know exactly what to do once home from the clinic.

**Frustrations:** Uncertainty about whether a symptom is urgent; forgetting or misremembering verbal instructions given at the clinic; not knowing which information sources to trust.

**Information needs:** Clear next actions; plain-language explanation of what happened at the visit; a simple, current checklist of home-care tasks.

**Technology comfort:** Comfortable with everyday consumer apps; not a technical user; prefers concise interactions over long reading.

**Trust concerns:** Wants confidence that AI-generated content will never be confused with the vet's actual instructions, and that urgent situations will be flagged clearly.

**Accessibility / usability needs:** Prefers concise explanations with clear next actions (stated communication preference); benefits from a low-friction, mobile-friendly interface usable while distracted or worried.

**Relevant journey stages:** `concern`, `conversation`, `triage`, `scheduling`, `home-care`, `follow-up`

**Representative quotation:** "I just want to know: is this something I need to worry about right now, and what exactly am I supposed to do once we're home?"

---

## 2. Dr. Maya Chen — Veterinarian

- **Role:** Veterinarian at Pine Ridge Veterinary Clinic
- **Associated case:** Sees Bailey for episode `episode-bailey-2026-07`

**Responsibilities:** Performs the clinical examination; determines the fictional assessment and diagnostic findings; approves the care plan and any veterinarian-approved instructions provided to the owner.

**Goals:** Spend appointment time on clinical judgment rather than re-collecting basic intake information; ensure the owner leaves with an accurate, unambiguous care plan.

**Frustrations:** Owners arriving with incomplete or disorganized symptom histories; any tool that risks presenting AI-generated content as her own clinical conclusion.

**Information needs:** A concise, structured summary of the owner's reported concern and timeline before or at the start of the visit; a clear way to enter and approve the care plan so it's unambiguously authoritative.

**Technology comfort:** Comfortable with clinic software in general; limited time per appointment, so needs information presented efficiently.

**Trust concerns:** Strongly needs AI-generated summaries and explanations to be clearly separated from her own diagnosis and instructions; will not accept a tool that blurs this line.

**Accessibility / usability needs:** Needs the clinic review view scannable in under a minute; minimal clicks to approve a care plan.

**Relevant journey stages:** `clinic`, `home-care`

**Representative quotation:** "Show me what the owner reported, but never show me something the system thinks is a diagnosis — that's my call."

---

## 3. Alex Rivera — Veterinary Technician

- **Role:** Veterinary technician at Pine Ridge Veterinary Clinic

**Responsibilities:** Reviews incoming structured summaries before appointments; supports scheduling and check-in; assists during the visit; helps monitor follow-up questions and adherence for the clinic.

**Goals:** Quickly triage which incoming concerns need same-day attention; keep the appointment schedule organized; flag unresolved owner concerns to Dr. Chen.

**Frustrations:** Incomplete owner-provided information; unclear which parts of a summary are AI-generated versus owner-stated fact.

**Information needs:** The structured clinic summary (symptom timeline, triage outcome); appointment details; visibility into post-visit adherence and any new follow-up questions.

**Technology comfort:** High comfort with clinic software and day-to-day operational tools.

**Trust concerns:** Needs confidence that escalation flags are reliable enough to prioritize same-day scheduling decisions.

**Accessibility / usability needs:** Needs a fast, list-oriented view suitable for use between other tasks during a busy clinic day.

**Relevant journey stages:** `scheduling`, `clinic`, `follow-up`

**Representative quotation:** "If it's flagged urgent, I need to trust that flag enough to bump the schedule — so it has to be conservative and consistent."

---

## 4. Sam Patel — Product Manager and QA Reviewer

- **Role:** Product manager and QA reviewer for the Pet Care Coach prototype

**Responsibilities:** Validates that the prototype's behavior matches documented features and acceptance criteria; checks that safety labeling and escalation behavior work as specified; prepares the prototype for demonstration.

**Goals:** Confirm every feature has traceable acceptance criteria; confirm no medication dosages or invented diagnoses ever appear; ensure the demo can be reset to a known state.

**Frustrations:** Undocumented behavior; inconsistent IDs or labels across files; features without clear success/failure conditions.

**Information needs:** A single place to see features, their acceptance criteria, and current demo data state (the product/QA evidence view); traceability between features and journey stages.

**Technology comfort:** High; comfortable reading structured requirements, JSON data, and test criteria directly.

**Trust concerns:** Needs assurance that safety constraints (no dosages, clear labeling, conservative escalation) are enforced consistently, not just described in prose.

**Accessibility / usability needs:** Needs clear keyboard navigation and structured, scannable views for efficient review sessions.

**Relevant journey stages:** All seven stages, reviewed cross-cutting via `follow-up` and the QA evidence view.

**Representative quotation:** "If I can't trace a feature to an acceptance criterion and a data source, I can't sign off on it."
