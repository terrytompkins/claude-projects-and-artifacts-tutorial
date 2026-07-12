# Pet Care Coach — Acceptance Criteria

*Grouped by feature. Canonical case: Jordan Lee, Bailey, episode `episode-bailey-2026-07`, Pine Ridge Veterinary Clinic. All clinical content is fictional demonstration data.*

## F-001 — Guided symptom conversation

- **AC-F001-01:** Given a new episode, when the owner starts a conversation, then the system asks structured clarifying questions covering onset, severity, frequency, appetite, and energy before producing a summary.
  - *Given* Jordan starts a new conversation about Bailey, *when* Jordan describes vomiting and low energy, *then* the system asks at least one clarifying question about onset and one about appetite before concluding the conversation.
- **AC-F001-02:** Given an incomplete answer, when the owner skips a clarifying question, then the system proceeds without inventing an answer and flags the field as unknown in the resulting summary.
- **AC-F001-03:** Given a completed conversation, when it ends, then a structured triage summary is produced and consumable by F-002 and F-003.

## F-002 — Safety and escalation messaging

- **AC-F002-01:** Given a conversation describing vomiting, reduced energy, and skipped meals, when triage runs, then the system returns an escalation level of "prompt, non-emergency" and recommends scheduling, labeled "AI-generated safety guidance — not a diagnosis."
  - *Given* the owner has described Bailey's symptoms, *when* the EscalationRule engine evaluates them, *then* the system displays an explicit escalation level and exactly one recommended next action.
- **AC-F002-02:** Given symptoms matching a red-flag rule, when triage runs, then the system displays an urgent banner directing the owner to contact the clinic immediately, and never states in absolute terms that the situation is not an emergency.
- **AC-F002-03:** Given any triage outcome, when displayed, then it is labeled "AI-generated safety guidance — not a diagnosis."

## F-003 — Structured clinic summary

- **AC-F003-01:** Given a completed conversation and triage summary, when a summary is generated, then it includes the symptom timeline, severity, and triage outcome, labeled "AI-generated summary — verify with owner."
- **AC-F003-02:** Given a conversation abandoned partway through, when a summary is requested, then the system generates a partial summary flagged as incomplete rather than failing silently.

## F-004 — Appointment request and scheduling

- **AC-F004-01:** Given a non-emergency triage outcome, when Jordan requests an appointment, then the system offers or accepts a request for a same-day illness visit and attaches the structured summary.
  - *Given* Jordan's episode has a non-emergency triage outcome, *when* Jordan submits an appointment request for July 15, 2026 at 2:30 PM, *then* the system creates an Appointment record with status "requested" or "confirmed" and visit type "same-day-illness."
- **AC-F004-02:** Given an urgent triage outcome, when the owner reaches the scheduling step, then the system redirects to direct clinic contact instead of standard scheduling.
- **AC-F004-03:** Given no same-day slots are available, when the owner requests one, then the system communicates the constraint clearly and offers the next available option rather than failing without explanation.

## F-005 — Clinic review view

- **AC-F005-01:** Given a confirmed appointment with an attached structured summary, when Alex opens the clinic review view, then the summary, triage outcome, and any flagged follow-up concerns are visible before the visit begins.
  - *Given* Bailey's appointment is confirmed for July 15, 2026, *when* Alex opens the clinic review view, *then* the AI-generated summary is visually distinguished from any clinic-entered notes.
- **AC-F005-02:** Given no structured summary exists for an episode, when staff open the clinic review view, then the view indicates no summary is available rather than showing a blank or broken state.

## F-006 — Diagnostic-result explanation

- **AC-F006-01:** Given clinician-entered diagnostic results for Bailey's visit, when the owner views them, then a plain-language explanation is shown alongside the original clinic-record entry, both correctly labeled.
  - *Given* the DiagnosticResult record shows "mild dehydration observed," *when* Jordan views the results, *then* the plain-language explanation restates only what the clinician recorded, without adding new clinical claims.
- **AC-F006-02:** Given a diagnostic result has not yet been entered, when the owner views the results screen, then the system indicates results are pending rather than displaying an empty or misleading state.

## F-007 — Home-care task list

- **AC-F007-01:** Given an approved care plan for episode `episode-bailey-2026-07`, when Jordan opens the home-care view, then all six tasks (`task-medication`, `task-water`, `task-small-meals`, `task-activity`, `task-monitor`, `task-followup`) are displayed, each labeled "veterinarian-approved."
  - *Given* Jordan opens the home-care task list, *when* Jordan marks `task-water` complete, *then* the task's status updates and a completion timestamp is recorded.
- **AC-F007-02:** Given a task marked complete, when Jordan un-marks it, then the status reverts and the completion timestamp is cleared.
- **AC-F007-03:** Given the care plan has not changed, when the task list is displayed, then no task text differs from the veterinarian-approved plan.

## F-008 — Follow-up question assistant

- **AC-F008-01:** Given Jordan asks a general recovery question, when the assistant responds, then the answer is labeled "AI-generated educational answer — not a diagnosis" and does not introduce a new treatment instruction.
  - *Given* Jordan asks "Is it okay that Bailey is drinking more water than usual?", *when* the assistant answers, *then* the response references the existing care plan and is labeled as an AI-generated educational answer.
- **AC-F008-02:** Given a follow-up question suggests worsening symptoms, when the assistant evaluates it, then the response escalates per F-002 rather than offering reassurance alone.
- **AC-F008-03:** Given any follow-up question, when submitted, then it is logged to the CareEpisode with its answer and `answeredBy` value.

## F-009 — Adherence and progress tracking

- **AC-F009-01:** Given task completion data for Bailey's episode, when Sam or clinic staff open the adherence view, then completion status for all six tasks is displayed accurately.
- **AC-F009-02:** Given an unresolved escalated follow-up question, when the adherence view is opened, then the unresolved concern is visibly flagged for clinic review.

## F-010 — Source and approval indicators

- **AC-F010-01:** Given any content block in the prototype, when rendered, then it carries exactly one label from the taxonomy: General educational information, Clinic-record information, Veterinarian-approved instructions, AI-generated summary, or Urgent escalation guidance (or a combination where content spans two sources).
  - *Given* the diagnostic-result explanation combines a clinic-record fact and an AI-generated explanation, *when* displayed, *then* both labels are shown, not just one.
- **AC-F010-02:** Given the CarePlan is displayed, when rendered, then it is labeled "veterinarian-approved" and visually distinguished from AI-generated content on the same screen.
- **AC-F010-03:** Given a user relies on assistive technology, when viewing any labeled content, then the label is conveyed through text or icon plus text, not color alone, and is readable by a screen reader.

## F-011 — Product and QA evidence view

- **AC-F011-01:** Given Sam opens the QA evidence view, when a feature is selected, then its linked acceptance-criteria IDs and relevant demo-data references are displayed.
- **AC-F011-02:** Given Sam triggers "reset demo state," when the reset completes, then all task completion status, follow-up questions, and adherence data return to the initial canonical state for `episode-bailey-2026-07`.
  - *Given* several tasks have been marked complete during a demo, *when* Sam clicks "reset demo state," *then* all six tasks return to "not started" and no follow-up questions remain logged.
- **AC-F011-03:** Given expected demo data is missing or fails to load, when the QA evidence view opens, then it displays a clear "data not loaded" state rather than a blank screen or silent failure.

---

## Traceability table

| AC ID | Feature | Journey stage(s) |
|---|---|---|
| AC-F001-01 | F-001 | `conversation` |
| AC-F001-02 | F-001 | `conversation` |
| AC-F001-03 | F-001 | `conversation` |
| AC-F002-01 | F-002 | `triage` |
| AC-F002-02 | F-002 | `triage` |
| AC-F002-03 | F-002 | `triage` |
| AC-F003-01 | F-003 | `conversation`, `triage` |
| AC-F003-02 | F-003 | `conversation` |
| AC-F004-01 | F-004 | `scheduling` |
| AC-F004-02 | F-004 | `scheduling` |
| AC-F004-03 | F-004 | `scheduling` |
| AC-F005-01 | F-005 | `clinic` |
| AC-F005-02 | F-005 | `clinic` |
| AC-F006-01 | F-006 | `clinic`, `home-care` |
| AC-F006-02 | F-006 | `clinic` |
| AC-F007-01 | F-007 | `home-care` |
| AC-F007-02 | F-007 | `home-care` |
| AC-F007-03 | F-007 | `home-care` |
| AC-F008-01 | F-008 | `follow-up` |
| AC-F008-02 | F-008 | `follow-up` |
| AC-F008-03 | F-008 | `follow-up` |
| AC-F009-01 | F-009 | `follow-up` |
| AC-F009-02 | F-009 | `follow-up` |
| AC-F010-01 | F-010 | `clinic`, `home-care` |
| AC-F010-02 | F-010 | `home-care` |
| AC-F010-03 | F-010 | `clinic`, `home-care` |
| AC-F011-01 | F-011 | `follow-up` |
| AC-F011-02 | F-011 | `follow-up` |
| AC-F011-03 | F-011 | `follow-up` |

This covers the required scenario areas: guided conversation (AC-F001-01), emergency escalation (AC-F002-02), non-emergency scheduling (AC-F004-01), clinic summary review (AC-F005-01), display of fictional diagnostics (AC-F006-01), home-care task completion (AC-F007-01), follow-up questions (AC-F008-01), source labeling (AC-F010-01), clinician-approval labeling (AC-F010-02), resetting the demonstration state (AC-F011-02), accessibility and keyboard navigation (AC-F010-03), and handling missing project data (AC-F005-02, AC-F006-02, AC-F011-03).
