# Pet Care Coach — Features and Requirements

*Canonical demonstration case: Jordan Lee (`owner-jordan-lee`) and Bailey (`pet-bailey`), episode `episode-bailey-2026-07`, at Pine Ridge Veterinary Clinic. All clinical details are fictional demonstration data.*

---

## F-001 — Guided symptom conversation

- **User story:** As Jordan, I want to describe Bailey's symptoms in a guided conversation so that I can get a clear recommendation for what to do next.
- **Functional requirements:** Structured prompts covering onset, severity, frequency, appetite, and energy; accepts free text; produces input consumable by triage (F-002) and the structured summary (F-003).
- **Edge cases:** Incomplete answers; contradictory answers; symptom described that isn't covered by scripted prompts.
- **Safety requirements:** Must not diagnose; must explicitly ask about known red-flag symptoms; must recommend professional care for anything ambiguous.
- **Source/approval indicators:** Labeled "AI-generated conversation — not a diagnosis."
- **Dependencies:** None (journey entry point).
- **Definition of done:** A completed conversation produces a structured triage summary consumable by F-002 and F-003.

## F-002 — Safety and escalation messaging

- **User story:** As Jordan, I want to be clearly told if Bailey's symptoms could be an emergency so I can act quickly.
- **Functional requirements:** Escalation-rule engine; urgent banner; direct-contact guidance for emergency scenarios.
- **Edge cases:** Borderline symptom combinations; owner disagrees with the escalation level; multiple symptoms with mixed urgency.
- **Safety requirements:** Conservative bias toward recommending care; never states in absolute terms that something is "not an emergency"; always gives one clear next action.
- **Source/approval indicators:** Labeled "AI-generated safety guidance — not a diagnosis."
- **Dependencies:** F-001.
- **Definition of done:** Every conversation ends with an explicit escalation level and next action.

## F-003 — Structured clinic summary

- **User story:** As Alex Rivera, I want a concise structured summary of the owner's conversation so I don't have to re-ask everything.
- **Functional requirements:** Converts the conversation and triage output into a structured summary (symptom timeline, severity, triage outcome); available to clinic staff at scheduling and clinic stages.
- **Edge cases:** Conversation abandoned partway through; conflicting details across multiple owner sessions.
- **Safety requirements:** Labeled "AI-generated summary — verify with owner."
- **Source/approval indicators:** AI-generated, unapproved by a clinician.
- **Dependencies:** F-001, F-002.
- **Definition of done:** The summary is available to clinic staff before or at check-in.

## F-004 — Appointment request and scheduling

- **User story:** As Jordan, I want to request or schedule a visit directly from the conversation so I don't have to start over on the phone.
- **Functional requirements:** Presents available slots or accepts a request; captures visit type; attaches the structured summary (F-003).
- **Edge cases:** No same-day slots available; owner requests an emergency slot; owner reschedules or cancels.
- **Safety requirements:** Emergency cases must be redirected to direct clinic contact, not routed through standard scheduling.
- **Source/approval indicators:** Once confirmed, the appointment record is clinic-record data.
- **Dependencies:** F-002, F-003.
- **Definition of done:** A confirmed appointment record exists with date/time, type, clinic, and veterinarian.

## F-005 — Clinic review view

- **User story:** As Dr. Chen or Alex, I want to review the owner's concern and any unresolved follow-up items before or during the appointment.
- **Functional requirements:** Displays the structured summary, triage outcome, and any flagged follow-up concerns; staff can mark items reviewed.
- **Edge cases:** No summary available (owner called in directly); multiple episodes for the same pet.
- **Safety requirements:** Staff review is required before treating the AI summary as accurate.
- **Source/approval indicators:** Distinguishes AI-generated summary content from clinic-entered notes.
- **Dependencies:** F-003.
- **Definition of done:** Staff can view the summary and mark it reviewed.

## F-006 — Diagnostic-result explanation

- **User story:** As Jordan, I want the diagnostic results explained in plain language so I understand what happened at the visit.
- **Functional requirements:** Takes clinician-entered diagnostic results and produces a plain-language explanation for the owner.
- **Edge cases:** Partial or ambiguous diagnostic notes; results not yet entered.
- **Safety requirements:** The explanation must never add clinical claims beyond what the clinician recorded.
- **Source/approval indicators:** Two-tier labeling — clinic-record data (source) plus AI-generated explanation (derived).
- **Dependencies:** Clinician-entered diagnostic result (data model), F-005.
- **Definition of done:** Every diagnostic result has an available plain-language explanation labeled with its source.

## F-007 — Home-care task list

- **User story:** As Jordan, I want a clear checklist of care tasks so I know exactly what to do for Bailey at home.
- **Functional requirements:** Displays the six canonical care tasks (`task-medication`, `task-water`, `task-small-meals`, `task-activity`, `task-monitor`, `task-followup`) tied to the vet-approved care plan; supports marking tasks complete.
- **Edge cases:** Undoing a completed task; task list must reflect only the vet-approved plan, never AI-added tasks.
- **Safety requirements:** Task text is sourced only from the vet-approved care plan, never AI-generated or modified.
- **Source/approval indicators:** Labeled "veterinarian-approved."
- **Dependencies:** Vet-approved care plan (data model), F-005.
- **Definition of done:** All six tasks render with correct labels, and completion state persists.

## F-008 — Follow-up question assistant

- **User story:** As Jordan, I want to ask follow-up questions about Bailey's recovery and get helpful, safe answers.
- **Functional requirements:** Answers general educational questions; references the care plan; escalates when a question suggests worsening symptoms.
- **Edge cases:** Question outside the scope of the care plan; question implies a new, unrelated concern; question implies an emergency.
- **Safety requirements:** Must never provide a new treatment instruction; must defer to F-002 escalation logic when appropriate.
- **Source/approval indicators:** Labeled "AI-generated educational answer — not a diagnosis."
- **Dependencies:** F-007, F-002.
- **Definition of done:** Follow-up questions are logged and either answered or escalated.

## F-009 — Adherence and progress tracking

- **User story:** As Sam Patel or clinic staff, I want to see how well the owner is following the care plan so unresolved issues can be caught.
- **Functional requirements:** Aggregates task completion status and follow-up flags into a simple adherence view.
- **Edge cases:** No tasks completed; tasks completed out of expected order; conflicting completion timestamps.
- **Safety requirements:** Adherence data is informational only and never auto-adjusts clinical instructions.
- **Source/approval indicators:** Derived from owner-entered completion data.
- **Dependencies:** F-007, F-008.
- **Definition of done:** The adherence view accurately reflects current task and follow-up state.

## F-010 — Source and approval indicators

- **User story:** As any user, I want to always know whether something is general information, clinic-record data, AI-generated, or veterinarian-approved.
- **Functional requirements:** A consistent visual labeling system applied across all views, using the taxonomy: General educational information, Clinic-record information, Veterinarian-approved instructions, AI-generated summary, Urgent escalation guidance.
- **Edge cases:** Content combining a clinic-record fact and an AI-generated explanation must display both labels.
- **Safety requirements:** Labeling must never be omitted for clinical or escalation content.
- **Source/approval indicators:** This feature *is* the indicator system.
- **Dependencies:** None (cross-cutting); consumed by F-003, F-005, F-006, F-007.
- **Definition of done:** Every content block in the prototype carries an explicit label from the taxonomy.

## F-011 — Product and QA evidence view

- **User story:** As Sam Patel, I want a view that surfaces acceptance criteria, feature IDs, and sample data so I can validate the prototype against requirements.
- **Functional requirements:** Displays the feature list with linked acceptance criteria and demo-data references; supports a "reset demo state" action.
- **Edge cases:** Missing acceptance criteria for a feature; demo data not loaded.
- **Safety requirements:** None beyond general data handling; this is an internal/QA-facing view, not owner-facing.
- **Source/approval indicators:** Internal tooling; not part of the owner-facing labeling taxonomy.
- **Dependencies:** `07_SAMPLE_DEMO_DATA.json`, `08_ACCEPTANCE_CRITERIA.md`.
- **Definition of done:** A QA reviewer can trace each feature to its acceptance criteria and reset the demo state.

---

## MVP feature grouping

F-001, F-002, F-003, F-004, F-005, F-007, F-010 — the core end-to-end flow (conversation through home-care) plus consistent labeling.

## Later-phase features

F-006, F-008, F-009, F-011 — diagnostic explanation, follow-up assistant, adherence tracking, and the QA evidence view.

## Explicit exclusions

- Real clinic system integration or live calendar syncing.
- Real user accounts, authentication, or payment processing.
- Medication dosage calculation or display.
- Actual emergency dispatch or communication with emergency services.
- Multi-pet households (v1 scope is a single pet per episode).
- Multi-clinic network features.

## Feature-to-journey-stage traceability matrix

| Feature | concern | conversation | triage | scheduling | clinic | home-care | follow-up |
|---|---|---|---|---|---|---|---|
| F-001 | ✔ | ✔ | | | | | |
| F-002 | ✔ | ✔ | ✔ | | | | |
| F-003 | | ✔ | ✔ | ✔ | ✔ | | |
| F-004 | | | | ✔ | | | |
| F-005 | | | | | ✔ | | ✔ |
| F-006 | | | | | ✔ | ✔ | |
| F-007 | | | | | | ✔ | |
| F-008 | | | | | | | ✔ |
| F-009 | | | | | | | ✔ |
| F-010 | | | | | ✔ | ✔ | |
| F-011 | | | | | | | ✔ |
