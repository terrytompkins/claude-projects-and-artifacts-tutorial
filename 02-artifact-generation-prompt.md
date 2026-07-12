# Prompt: Generate the Pet Care Coach Journey Explorer Artifact

Run this prompt inside the completed **Pet Care Coach Product Workspace** Claude Project.

For presentation reliability, generate and verify the Artifact before class. During the live session, show the completed version and make one controlled enhancement using the prompts in `03-live-demo-prompts.md`.

## Build and verification strategy

This prompt asks for a substantial application in one pass. Treat the first response as a draft, not a finished result:

1. Run the prompt below once, in full.
2. Work through the "Functional verification" checklist near the end of this file item by item, actually clicking/toggling each control rather than reading the code.
3. For anything that fails, don't ask for a full regeneration. Describe only the specific broken behavior and ask Claude to fix it in place — the emergency repair prompt in `03-live-demo-prompts.md` is written for exactly this and can be reused here during prep, not just during class.
4. Budget at least one extra iteration pass before you consider the Artifact done. Don't verify only once and assume it will hold up live.

---

## Prompt

Create an interactive React Artifact titled:

# Pet Care Coach Journey Explorer

Use the uploaded Pet Care Coach Project knowledge as the authoritative source. In particular, use:

- `01_PRODUCT_OVERVIEW.md`
- `02_PERSONAS.md`
- `03_END_TO_END_JOURNEY.md`
- `04_FEATURES_AND_REQUIREMENTS.md`
- `06_CONTENT_AND_SAFETY_GUIDELINES.md`
- `07_SAMPLE_DEMO_DATA.json`
- `08_ACCEPTANCE_CRITERIA.md`

Do not invent clinical facts, dosages, veterinary recommendations, identifiers, journey stages, or acceptance criteria that are absent from the project knowledge.

Create the working Artifact now. Do not begin with a design proposal or ask clarifying questions.

## Technical constraints

Build a complete single-page React Artifact.

Use:

- React
- Standard browser capabilities
- Local component state
- Inline styles, a style element, or self-contained CSS
- Inline SVG or Unicode symbols when icons are helpful

Do not require:

- An external API
- A database
- MCP
- Authentication
- An npm installation step
- External images
- External fonts
- Network access
- Additional files

The Artifact must work immediately in Claude’s Artifact preview.

Use the exact records and IDs from `07_SAMPLE_DEMO_DATA.json`. Treat the Project files as authoritative when they contain more detail than the JSON.

## Visual and interaction goals

The application should look like a credible, polished product prototype rather than a developer debugging page.

Design for a projected classroom display:

- High contrast
- Readable typography
- Generous spacing
- Large clickable controls
- Clear selected states
- Responsive behavior
- No dense walls of text
- Keyboard-accessible controls
- Visible focus states
- Appropriate ARIA labels

Use a calm professional visual style suitable for pet-owner and veterinary-clinic software. Do not make it childish or overly decorative.

Display a persistent label near the top:

**Fictional demonstration data — not veterinary advice**

## Application structure

### 1. Header

Show:

- Pet Care Coach Journey Explorer
- Bailey’s name, species, breed, and age
- Jordan Lee as owner
- The current care episode status
- The fictional-data notice
- A `Reset demo` button

Resetting must restore all local interaction state, including completed tasks, selected tabs, selected journey stage, and expanded panels.

### 2. Perspective selector

Provide three perspective buttons:

- Pet Owner
- Clinic Team
- Product & QA

Changing perspective must meaningfully change the content displayed for the selected journey stage.

#### Pet Owner perspective

Emphasize:

- Goal
- Questions
- Emotion
- Next action
- Plain-language explanation
- Trust and safety indicators

#### Clinic Team perspective

Emphasize:

- Structured information received
- Human review responsibility
- Handoff details
- Source and approval status
- Follow-up concerns

#### Product & QA perspective

Emphasize:

- Feature IDs
- Data captured
- Acceptance-criteria IDs
- Failure conditions
- Safety requirements
- Product opportunities

### 3. Journey navigation

Display all seven canonical journey stages in the correct order:

1. Notice a Concern
2. Describe the Symptoms
3. Determine the Next Step
4. Schedule the Visit
5. Clinic Evaluation
6. Follow the Care Plan
7. Monitor and Follow Up

Use the canonical stage IDs from the knowledge base.

The navigation may be a horizontal stepper on wide screens and a compact stacked or scrollable control on narrow screens.

Selecting a stage must update the main detail panel without reloading the page.

Show a clear visual distinction between:

- Completed stages
- Current stage
- Future stages

For the demonstration episode, set `Follow the Care Plan` as the initial selected and current stage.

### 4. Journey detail panel

For the selected stage, show:

- Stage name
- Owner goal
- Owner emotion
- Key questions
- Pain point
- System behavior
- Human responsibility
- Safety consideration
- Product opportunity
- Relevant features

Adapt the emphasis to the selected perspective.

Avoid presenting unsupported health guidance.

### 5. Main content tabs

Create the following tabs:

- Journey
- Home Care
- Evidence

#### Journey tab

Display the journey navigation and detail panel described above.

#### Home Care tab

Show Bailey’s six canonical home-care tasks using the exact task IDs and veterinarian-approved wording from the project knowledge.

For each task display:

- Task title
- Owner-friendly explanation
- Source type
- Approval status
- Completion control

Allow each task to be marked complete or incomplete.

Show:

- Completed count
- Total count
- Progress percentage
- Accessible progress indicator

Do not add medication dosage or treatment details.

Include a clear reminder that the clinic label and veterinarian’s instructions are authoritative.

#### Evidence tab

Show a product-evidence view suitable for teaching how the Artifact was grounded.

Include:

- Project filename
- Relevant section or record
- Related feature IDs
- Related journey-stage IDs
- Related acceptance-criteria IDs
- Source type
- Approval status

Provide filters for:

- Product requirements
- Journey information
- Safety guidance
- Sample data
- Acceptance criteria

Do not claim a source unless the information exists in that Project file.

### 6. Source and approval badges

Use consistent badges for:

- AI-generated summary
- Owner-provided information
- Clinic record
- Veterinarian-approved instruction
- Fictional demonstration data

Do not rely on color alone to communicate the badge meaning.

### 7. Follow-up question examples

In the `Monitor and Follow Up` stage, show the three sample follow-up questions from the JSON.

Selecting a question should display a safe mock response constructed only from the approved project content.

The response must:

- Identify its source type
- State when the owner should contact the clinic
- Avoid diagnosis
- Avoid dosage
- Defer to veterinarian-approved instructions

This should be deterministic local behavior, not an external model call.

### 8. Product teaching panel

Include a collapsible panel named:

**How this Artifact uses the Project**

When opened, explain briefly:

- The Project stores shared product context.
- The Artifact turns that context into an interactive experience.
- Journey information comes from the journey file.
- Sample records come from the JSON file.
- Safety behavior comes from the safety-guidelines file.
- QA evidence comes from the acceptance-criteria file.

Keep this panel concise and presentation-friendly.

## Functional verification

Before finalizing the Artifact, verify that:

- Every tab works.
- Every journey-stage control works.
- Every perspective control works.
- All six care tasks can be toggled.
- Progress updates correctly.
- Reset restores initial state.
- Evidence filters work.
- Follow-up examples work.
- No control depends on a missing library.
- No console-breaking reference is apparent.
- No medication dosage appears.
- All clinical details are visibly labeled fictional.
- All major product claims are traceable to Project files.

Produce the Artifact directly, then provide only a brief note describing the completed interactions and any assumptions.
