# Prompt: Create the Pet Care Coach Claude Project Workspace

Run this prompt in a normal Claude conversation before the class.

This is split into **two parts, run one after another in the same chat** (Part 2 depends on Part 1's conversation context). Wait for Part 1 to fully finish, review it briefly, then paste Part 2 into the same conversation. Do not start a new chat for Part 2 — it deliberately does not repeat the product scenario, canonical case, journey stages, or feature list, and instead reuses what Part 1 already established.

After both parts finish:

1. Create a Claude Project named **Pet Care Coach Product Workspace**.
2. Copy the contents of `00_PROJECT_INSTRUCTIONS.md` into the Project Instructions field.
3. Upload the other ten generated files as Project Knowledge.

---

## Part 1 of 2 — Foundational files

### Prompt (Part 1)

Create a complete, internally consistent knowledge bundle for a fictional product named **Pet Care Coach**.

Pet Care Coach is an educational prototype used to demonstrate generative AI product-design techniques. It helps pet owners understand and follow veterinary care instructions before and after a clinic visit. It does not diagnose conditions or replace a veterinarian.

The bundle will be uploaded to a Claude Project and later used to generate an interactive React Artifact. The files must therefore contain enough specific, structured, consistent information for Claude to answer product questions and construct a working application without inventing important details.

This is Part 1 of a two-part generation. In this part, produce only the following six files. A second prompt will add the remaining files afterward in this same conversation, reusing the facts, IDs, and names established here.

### Output requirements (Part 1)

Create each of the following as a separate downloadable file when the interface supports file creation. Otherwise, place each file in its own clearly labeled fenced code block.

Use the exact filenames shown below:

1. `00_PROJECT_INSTRUCTIONS.md`
2. `01_PRODUCT_OVERVIEW.md`
3. `02_PERSONAS.md`
4. `03_END_TO_END_JOURNEY.md`
5. `04_FEATURES_AND_REQUIREMENTS.md`
6. `05_DOMAIN_AND_DATA_MODEL.md`

Before producing the files, silently create a consistency checklist. Verify that names, identifiers, journey-stage identifiers, feature identifiers, pet information, appointment details, and sample results are identical wherever they appear.

Do not describe what you plan to do. Produce the finished files.

---

# Product scenario

Pet Care Coach supports the following end-to-end journey:

1. A pet owner notices a health concern.
2. The owner uses an AI-assisted conversation to describe symptoms.
3. The system asks appropriate clarifying questions and identifies whether urgent escalation may be needed.
4. For non-emergency scenarios, the owner can request or schedule a clinic appointment.
5. The clinic receives a concise, structured summary of the conversation.
6. Clinic staff review the concern and conduct the appointment.
7. Diagnostic results and veterinarian-approved care instructions are added.
8. The owner returns home with a clear care plan.
9. The owner tracks care tasks and asks follow-up questions.
10. The clinic can review adherence and unresolved concerns.

The product must clearly distinguish:

- General educational information
- Information retrieved from the pet's clinic record
- Veterinarian-approved instructions
- Urgent escalation guidance
- AI-generated summaries

The application must never represent an AI-generated suggestion as a veterinary diagnosis or veterinarian-approved instruction.

---

# Canonical demonstration case

Use this fictional case consistently across all files.

## Owner

- ID: `owner-jordan-lee`
- Name: Jordan Lee
- Preferred name: Jordan
- Communication preference: concise explanations with clear next actions
- Primary concern: uncertainty about what to do after returning home from the clinic

## Pet

- ID: `pet-bailey`
- Name: Bailey
- Species: Dog
- Breed: Labrador Retriever
- Age: 6 years
- Weight: 68 pounds
- Sex: Female, spayed
- Known sensitivity: rich or fatty food
- Primary clinic: Pine Ridge Veterinary Clinic

## Current episode

- Episode ID: `episode-bailey-2026-07`
- Initial owner concern: Bailey vomited twice, seemed less energetic than usual, and did not finish breakfast.
- Demonstration classification: prompt veterinary evaluation was appropriate, but the fictional scenario was not classified as an immediate emergency.
- Appointment date and time: July 15, 2026 at 2:30 PM
- Appointment type: Same-day illness visit
- Clinic: Pine Ridge Veterinary Clinic
- Veterinarian: Dr. Maya Chen
- Fictional assessment: gastrointestinal irritation with mild dehydration
- Fictional diagnostic summary:
  - Physical examination completed
  - Mild dehydration observed
  - Abdominal imaging did not show evidence of an obstructive foreign object
  - Laboratory results did not identify a critical abnormality
- Treatment summary:
  - Fluids administered at the clinic
  - Veterinarian-approved anti-nausea medication provided
  - Temporary bland-diet instructions provided
  - Activity and symptom-monitoring instructions provided
- No medication dosage may appear in the knowledge bundle.
- All clinical details must be labeled as fictional demonstration data.

## Home-care tasks

Use these exact task IDs:

- `task-medication`
- `task-water`
- `task-small-meals`
- `task-activity`
- `task-monitor`
- `task-followup`

The tasks are:

1. Give the veterinarian-approved medication according to the clinic label.
2. Offer access to water and follow the clinic's hydration instructions.
3. Offer small meals according to the veterinarian-approved diet instructions.
4. Keep activity calm for the remainder of the day.
5. Monitor vomiting, energy, water intake, appetite, and other changes identified by the clinic.
6. Complete the scheduled clinic follow-up or contact the clinic sooner when escalation criteria are met.

Do not add medical dosages, new treatment instructions, or unsupported home remedies.

---

# Required journey stages

Use these exact identifiers and labels in all applicable files:

| Stage ID | Stage label |
|---|---|
| `concern` | Notice a Concern |
| `conversation` | Describe the Symptoms |
| `triage` | Determine the Next Step |
| `scheduling` | Schedule the Visit |
| `clinic` | Clinic Evaluation |
| `home-care` | Follow the Care Plan |
| `follow-up` | Monitor and Follow Up |

For each journey stage, define:

- Owner goal
- Owner questions
- Owner emotion
- Pain point
- System behavior
- Human responsibility
- Data captured
- Safety consideration
- Product opportunity
- Relevant feature IDs

---

# Required product features

Use stable feature IDs beginning with `F-`.

At minimum, define these features:

- `F-001`: Guided symptom conversation
- `F-002`: Safety and escalation messaging
- `F-003`: Structured clinic summary
- `F-004`: Appointment request and scheduling
- `F-005`: Clinic review view
- `F-006`: Diagnostic-result explanation
- `F-007`: Home-care task list
- `F-008`: Follow-up question assistant
- `F-009`: Adherence and progress tracking
- `F-010`: Source and approval indicators
- `F-011`: Product and QA evidence view

For each feature include:

- Purpose
- Primary users
- Inputs
- Outputs
- Main success condition
- Failure conditions
- Safety constraints
- Related journey stages

---

# File-specific instructions (Part 1)

## `00_PROJECT_INSTRUCTIONS.md`

Write copy-ready instructions for the Claude Project's **Set project instructions** field.

The instructions must tell Claude to:

- Act as a product strategist, UX analyst, business analyst, and prototype assistant for Pet Care Coach.
- Ground factual product answers in the uploaded project knowledge.
- Distinguish facts from proposals and assumptions.
- Cite the relevant project filename and section when making product claims.
- Use exact IDs from the project files.
- Never invent veterinary diagnoses, medication dosages, or treatment instructions.
- Label all health scenarios as fictional demonstration material.
- Identify contradictions between files rather than silently resolving them.
- Prefer concise, presentation-friendly output unless asked for depth.
- Support product, UX, architecture, QA, and training perspectives.
- Produce accessible interfaces and plain-language owner content.
- Treat the veterinarian-approved care plan as authoritative over AI-generated content.

Make the instructions approximately 400–700 words.

## `01_PRODUCT_OVERVIEW.md`

Include:

- Product vision
- Problem statement
- Target users
- Value proposition
- Goals
- Non-goals
- Major capabilities
- Success measures
- Product principles
- Current prototype scope
- Explicit assumptions
- Risks and limitations

Clearly state that this is an educational prototype.

## `02_PERSONAS.md`

Create four personas:

1. Jordan Lee — pet owner
2. Dr. Maya Chen — veterinarian
3. Alex Rivera — veterinary technician
4. Sam Patel — product manager and QA reviewer

For each persona include:

- Responsibilities
- Goals
- Frustrations
- Information needs
- Technology comfort
- Trust concerns
- Accessibility or usability needs
- Relevant journey stages
- Representative quotation

Keep the personas useful for product decisions rather than making them marketing caricatures.

## `03_END_TO_END_JOURNEY.md`

Create:

- A journey summary
- A detailed table using all seven canonical stages
- The required fields for each stage
- Key handoffs between owner, AI, clinic staff, and veterinarian
- Moments where the system must defer to a human
- A Mermaid flowchart of the complete journey
- Three major design opportunities
- Three major safety risks

Ensure the Mermaid syntax is valid and simple.

## `04_FEATURES_AND_REQUIREMENTS.md`

Document all required features.

For each feature provide:

- Feature ID and name
- User story
- Functional requirements
- Important edge cases
- Safety requirements
- Source or approval indicators
- Dependencies
- Definition of done

Also include:

- MVP feature grouping
- Later-phase features
- Explicit exclusions
- A feature-to-journey-stage traceability matrix

## `05_DOMAIN_AND_DATA_MODEL.md`

Define the conceptual entities:

- Owner
- Pet
- Clinic
- StaffMember
- CareEpisode
- Conversation
- ConversationMessage
- TriageSummary
- Appointment
- ClinicVisit
- DiagnosticResult
- CarePlan
- CareTask
- FollowUpQuestion
- EscalationRule
- SourceReference

For each entity provide:

- Purpose
- Important fields
- Relationships
- Data ownership
- Sensitivity classification
- Retention considerations

Include:

- A Mermaid entity-relationship diagram
- A compact JSON shape illustrating a complete CareEpisode
- A description of which records contain AI-generated content and which contain clinician-approved content

Do not create a production legal or compliance claim.

---

# Quality checks (Part 1)

Before finishing this part:

1. Confirm all seven journey stages appear consistently across all six files.
2. Confirm all eleven feature IDs (`F-001`–`F-011`) appear consistently wherever features are discussed.
3. Confirm all six care-task IDs appear consistently wherever home-care tasks are discussed.
4. Confirm no medication dosage appears anywhere.
5. Confirm all clinical details are labeled as fictional demonstration data.
6. Validate both Mermaid diagrams (the journey flowchart in `03_END_TO_END_JOURNEY.md` and the entity-relationship diagram in `05_DOMAIN_AND_DATA_MODEL.md`) for obvious syntax problems.
7. Confirm `00_PROJECT_INSTRUCTIONS.md` explicitly tells Claude to cite project filenames and sections when making product claims.
8. Confirm none of these six files contradicts another.

After the files, provide a short validation note listing the checks performed and any assumptions made. Then stop and wait for Part 2.

---

## Part 2 of 2 — Data, criteria, and demo materials

Paste this into the **same chat** after Part 1 has finished.

### Prompt (Part 2)

Continue building the Pet Care Coach knowledge bundle using the exact product scenario, canonical demonstration case, journey stages, and features already established above in this conversation. Do not restate them or introduce new names, IDs, or facts that conflict with what was already generated.

Produce the remaining five files now:

1. `06_CONTENT_AND_SAFETY_GUIDELINES.md`
2. `07_SAMPLE_DEMO_DATA.json`
3. `08_ACCEPTANCE_CRITERIA.md`
4. `09_DEMO_QUESTIONS.md`
5. `README.md`

**Before writing any of these files**, internally define the complete list of acceptance-criteria IDs that will appear in `08_ACCEPTANCE_CRITERIA.md` (at least 25, grouped by feature, using IDs such as `AC-F001-01`, `AC-F001-02`). Use only IDs from that same list if `07_SAMPLE_DEMO_DATA.json` references acceptance criteria — a small subset (3–5 IDs) is sufficient there; do not invent additional ad hoc IDs in the JSON file.

Do not describe what you plan to do. Produce the finished files.

---

# File-specific instructions (Part 2)

## `06_CONTENT_AND_SAFETY_GUIDELINES.md`

Include:

- Voice and tone
- Plain-language principles
- Required uncertainty language
- Emergency and escalation presentation
- Prohibited content
- How to label AI-generated summaries
- How to label clinic-record information
- How to label veterinarian-approved instructions
- Source hierarchy
- Accessibility guidance
- Privacy reminders
- Example acceptable messages
- Example unacceptable messages with corrected alternatives

The hierarchy must place direct veterinarian instructions above AI summaries.

## `07_SAMPLE_DEMO_DATA.json`

Create valid JSON, not JSON with comments.

It must include:

- Product metadata
- All four personas
- Jordan
- Bailey
- Pine Ridge Veterinary Clinic
- Dr. Maya Chen
- Alex Rivera
- The complete care episode
- All seven journey stages
- The appointment
- The clinic visit
- Fictional diagnostic results
- The care plan
- All six home-care tasks
- Three follow-up questions
- Source references
- Relevant acceptance-criteria IDs (a small subset — see the note above)
- A small set of demonstration metrics

Every record must have a stable ID.

Include fields that distinguish:

- `sourceType`
- `approvalStatus`
- `generatedBy`
- `lastUpdated`

Use ISO 8601 dates and times.

Ensure the JSON can be parsed successfully.

## `08_ACCEPTANCE_CRITERIA.md`

Create acceptance criteria grouped by feature, using the exact ID list you defined before starting this part.

Use IDs such as:

- `AC-F001-01`
- `AC-F001-02`

Include at least 25 acceptance criteria.

For the most important workflows, include Given/When/Then scenarios covering:

- Guided conversation
- Emergency escalation
- Non-emergency scheduling
- Clinic summary review
- Display of fictional diagnostics
- Home-care task completion
- Follow-up questions
- Source labeling
- Clinician approval labeling
- Resetting the demonstration state
- Accessibility and keyboard navigation
- Handling missing project data

Include a traceability table connecting criteria to features and journey stages.

## `09_DEMO_QUESTIONS.md`

Create a demonstration runbook containing:

### Normal-chat comparison prompt

A short prompt that asks Claude to propose a Pet Care Coach experience without access to the project knowledge.

### Project-grounded prompts

Create prompts that ask Claude to:

1. Summarize the product for an executive.
2. Explain Jordan and Bailey's journey.
3. Identify the most important product risk.
4. Produce a QA test plan for the home-care stage.
5. Compare the needs of Jordan, Dr. Chen, and Alex.
6. Identify the sources for every significant claim.
7. Prepare to create an interactive Artifact.

For each demonstration prompt include:

- What it demonstrates
- Expected evidence from the knowledge base
- A likely follow-up prompt

### Demo facilitation notes

Include:

- Which prompts are best to run live
- Which responses should be generated in advance
- What to point out to a mixed audience
- A fallback approach if generation takes too long

## `README.md`

Explain:

- What the bundle contains
- How to create the Claude Project
- Which file to copy into Project Instructions
- Which files to upload as Project Knowledge
- How to verify that the Project is using its knowledge
- Recommended order for the live demonstration
- Which files are the authoritative sources for product, journey, safety, data, and acceptance criteria
- A five-minute pre-class verification checklist

End the README with a file consistency matrix.

---

# Quality checks (Part 2)

Before finishing:

1. Validate `07_SAMPLE_DEMO_DATA.json` syntactically.
2. Confirm all seven journey stages appear consistently, matching Part 1 exactly.
3. Confirm all required feature IDs appear, matching Part 1 exactly.
4. Confirm all six care-task IDs appear, matching Part 1 exactly.
5. Confirm no medication dosage appears in any of these five files.
6. Confirm all clinical details in these five files are labeled fictional.
7. Confirm every acceptance-criteria ID referenced in `07_SAMPLE_DEMO_DATA.json` is defined in `08_ACCEPTANCE_CRITERIA.md`, and that all acceptance criteria reference valid feature and stage IDs.
8. Confirm none of these five files contradicts each other or any file from Part 1.

After the files, provide a short validation report listing the checks performed and any assumptions made, covering both Part 1 and Part 2.
