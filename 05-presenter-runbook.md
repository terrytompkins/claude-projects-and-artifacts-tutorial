# Presenter Runbook

## Session

**Beyond the Chat: Building Reusable Workspaces and Apps with Claude Projects and Artifacts**

## Duration

30 minutes

## Demo product

**Pet Care Coach Product Workspace**

---

# 1. Preparation checklist

## Before the session

- [ ] Run Part 1 of `01-project-workspace-prompt.md`, then Part 2 in the same chat.
- [ ] Review all generated files for consistency.
- [ ] Validate that `07_SAMPLE_DEMO_DATA.json` is valid JSON.
- [ ] Create the Claude Project.
- [ ] Copy `00_PROJECT_INSTRUCTIONS.md` into Project Instructions.
- [ ] Upload the remaining files as Project Knowledge.
- [ ] Run `02-artifact-generation-prompt.md`.
- [ ] Verify every Artifact interaction against its functional-verification checklist; use the emergency repair prompt in `03-live-demo-prompts.md` for anything that fails, and budget at least one iteration pass.
- [ ] Perform a keyboard-only pass through the Artifact (Tab / Shift+Tab / Enter / Space) to confirm focus states and control operability.
- [ ] Save the completed Artifact.
- [ ] Run Prompt A and Prompt B once in advance.
- [ ] Run the QA Coverage enhancement once in advance, and time how long it actually takes to sanity-check the 24:00 hard cutoff.
- [ ] Capture screenshots of:
  - Project file list
  - Journey tab
  - Home Care tab
  - Evidence tab
  - QA Coverage Mode
- [ ] Add screenshots as hidden backup slides.

## Day of the session

- [ ] Sign in to Claude.
- [ ] Open the Pet Care Coach Project.
- [ ] Open the completed Artifact in a separate tab.
- [ ] Open two empty chats inside the Project.
- [ ] Open `03-live-demo-prompts.md`.
- [ ] Open the slide deck.
- [ ] Increase browser zoom for projected readability.
- [ ] Close unrelated browser tabs and notifications.
- [ ] Confirm network access.
- [ ] Confirm the Artifact reset button works.
- [ ] Confirm the Project files are visible.
- [ ] Confirm the prebuilt QA-enhanced Artifact remains available as a fallback.

---

# 2. Demo environment layout

Recommended browser tabs:

1. Slide deck
2. Claude Project home
3. Project Chat A
4. Project Chat B
5. Prebuilt Journey Explorer Artifact
6. Prebuilt QA-enhanced Artifact
7. Live Demo Prompts Markdown file

Keep the prebuilt QA-enhanced version separate from the Artifact you plan to modify live.

---

# 3. Detailed timing and speaking notes

## 0:00–0:03 — Slides 1 and 2

### Slide 1: Beyond the Chat

Suggested opening:

> Most of us begin using generative AI one conversation at a time. That works well for isolated questions, but it becomes inefficient when the work has shared terminology, reference material, safety constraints, and multiple stakeholders.

> Today I want to show a simple progression: a chat answers a question, a Project creates a reusable workspace, and an Artifact turns that workspace into something interactive.

Do not spend time explaining every possible Claude feature.

### Slide 2: What Persists Where?

Suggested explanation:

> A Project separates three things we often mix together: the current conversation, reusable instructions, and reusable knowledge.

> That means I can open several chats for different tasks without copying the same product background into every prompt.

> An Artifact is a separate idea. It is a substantial output—such as a document, visualization, or application—created from that context.

Transition:

> Let’s look at a small fictional product workspace.

---

## 0:03–0:07 — Explore the Project

Open **Pet Care Coach Product Workspace**.

Show the Project Instructions briefly.

Say:

> These instructions define how Claude should work in this particular workspace. They establish roles, grounding expectations, source citation, accessibility, and safety boundaries.

Do not read the complete instructions.

Show the Project Knowledge file list.

Briefly identify:

- Product overview
- Personas
- Journey
- Requirements
- Safety guidance
- Demo data
- Acceptance criteria

Say:

> This is not intended to be an enormous document repository. It is a curated body of knowledge for a specific product.

> The important point is that these files now become available to multiple conversations inside the Project.

Optional audience question:

> Which of these files would your own team already have in some form?

Avoid allowing discussion to consume more than 30 seconds.

---

## 0:07–0:12 — Two grounded chats

### Project Chat A

Run Prompt A from `03-live-demo-prompts.md`.

While the response appears, explain:

> Notice that I did not repeat the personas, journey stages, product features, or safety rules in the prompt. I asked for a task, while the Project supplied the background.

When the answer completes, point out:

- Exact journey-stage names
- Human responsibility
- Safety considerations
- Source filenames

Do not review every row.

### Project Chat B

Switch to a different chat inside the same Project.

Run Prompt B.

Explain:

> This is a separate conversation. It does not depend on the immediate conversation history from the first chat, but it uses the same Project Knowledge.

Point out:

- Different stakeholder perspectives
- Feature IDs
- Acceptance-criteria IDs
- Source and approval distinctions

Core teaching point:

> The Project is not simply a long chat. It is a reusable context boundary for a body of work.

### Timing fallback

If Prompt A takes too long:

- Show a pre-generated response.
- Skip Prompt B live.
- Summarize the second use case verbally.

Move to the Artifact no later than 12:00.

---

## 0:12–0:19 — Explore the existing Artifact

Open the completed **Pet Care Coach Journey Explorer**.

Say:

> Now we move from grounded conversation to a reusable experience.

### Show the header

Point out:

- Fictional demonstration label
- Owner and pet
- Current care episode
- Reset control

### Show the Journey tab

Demonstrate:

- Selecting two or three journey stages
- Switching from Pet Owner to Clinic Team
- Switching to Product & QA

Say:

> The same journey is being represented differently for each audience. The underlying facts remain consistent, but the emphasis changes.

### Show the Home Care tab

Toggle two tasks.

Point out:

- Progress updates
- Source type
- Approval status
- No invented dosage or treatment content

Say:

> This is a useful distinction in AI-enabled products: what was generated by AI, what came from the owner, what came from the clinic record, and what was approved by the veterinarian.

### Show the Evidence tab

Apply one filter.

Point out:

- Project filename
- Feature ID
- Journey-stage ID
- Acceptance-criteria ID

Say:

> This is the bridge from an attractive prototype to a traceable product conversation.

### Timing fallback

If interactions are slow, show only:

1. Perspective switching
2. One care-task toggle
3. Evidence tab

Move to the enhancement no later than 19:00.

---

## 0:19–0:25 — Add QA Coverage Mode

Switch to Product & QA perspective.

Paste Prompt C from `03-live-demo-prompts.md`.

Before submitting, highlight one sentence:

> “This must be an enhancement to the existing Artifact, not a replacement application.”

Explain:

> That instruction matters. A weak iteration prompt often causes a model to rebuild the application and accidentally remove working behavior.

Submit the prompt.

While Claude works, explain what the model already has:

- Existing React Artifact
- Journey-stage IDs
- Feature IDs
- Acceptance criteria
- Project source files
- Product safety rules

Say:

> I am asking for a product change, not restating the entire product.

When the change completes, demonstrate:

- Product & QA perspective
- QA Coverage toggle
- Coverage summary
- Coverage filter
- One Given/When/Then scenario
- Reset behavior

### Hard time boundary

If the update is not ready by 24:00:

1. Stop waiting.
2. Open the prebuilt QA-enhanced Artifact.
3. Say:

> I ran the same enhancement in advance so we can inspect the result rather than spend the remainder of the session watching generation.

This is not a failure. It reinforces good demo practice.

---

## 0:25–0:28 — Slide 3

Return to **What We Just Built**.

Summarize:

> We started with structured product knowledge.

> We reused it across different conversations.

> We converted it into an interactive application.

> We then added a QA feature using acceptance criteria already stored in the Project.

Emphasize:

- Reusable context
- Cross-functional use
- Traceability
- Iterative artifact development

Avoid implying that the Artifact is automatically production-ready.

Suggested caution:

> This is still a prototype. Generated code and product logic require review, testing, security analysis, and normal engineering practices before production use.

---

## 0:28–0:30 — Slide 4 and close

Use the feature decision table.

Suggested close:

> Use a normal chat when the task is isolated.

> Use a Project when the work has shared knowledge, vocabulary, instructions, or multiple conversations.

> Use an Artifact when the output should become something reusable or interactive.

> The broader lesson is that once work becomes repeatable, shared, or multi-step, we should stop treating it as an isolated prompt.

Final sentence:

> Move reusable context into a Project, then turn the most useful results into Artifacts.

---

# 4. Demonstration checkpoints

## Project checkpoint

The audience should see:

- Project Instructions
- Multiple knowledge files
- Two different chats
- Reuse of exact IDs and facts

## Artifact checkpoint

The audience should see:

- Interactive journey
- Multiple perspectives
- Task state
- Evidence and provenance
- One iterative enhancement

## Teaching checkpoint

The audience should leave with these distinctions:

| Concept | Meaning |
|---|---|
| Chat context | The immediate conversation |
| Project Instructions | Persistent behavior and constraints |
| Project Knowledge | Persistent reusable reference material |
| Artifact | A substantial reusable output |
| Live enhancement | Iteration on the existing output |

---

# 5. Common questions and suggested answers

## “Does every chat in the Project automatically know what another chat said?”

Not necessarily. The shared Project Instructions and Project Knowledge are reusable across Project chats, but you should not treat ordinary conversation history as shared knowledge. Important facts should be added to the Project’s knowledge rather than left only in one conversation.

## “Is an Artifact a production application?”

Usually, it should be treated as a prototype or working demonstration unless it has gone through normal engineering, security, accessibility, testing, deployment, and operational review.

## “Could the Artifact call APIs or enterprise systems?”

Potentially, depending on the available Claude and Artifact capabilities, but this demonstration intentionally avoids external dependencies. That keeps the focus on Projects, grounding, and interaction design.

## “Why use files instead of one large project prompt?”

Files create separable, maintainable sources. Product overview, safety guidance, sample data, and acceptance criteria can be updated independently and cited more clearly.

## “How is this different from RAG?”

A Claude Project may use retrieval techniques behind the scenes as its knowledge grows, but the user-facing lesson here is simpler: Projects provide a curated reusable workspace. A production RAG architecture involves additional choices around ingestion, chunking, retrieval, ranking, authorization, evaluation, and operations.

## “Could a team use the same Project?”

Team and plan capabilities may vary. The architectural idea still applies: curate shared instructions and knowledge, then create role-specific conversations and outputs from them.

---

# 6. Failure recovery

## Claude response is slow

- Use a pre-generated response.
- Explain what the live prompt was intended to demonstrate.
- Continue to the Artifact.

## Artifact fails to render

- Use the emergency repair prompt.
- If repair is not immediate, open the prebuilt Artifact or backup screenshot.

## Live enhancement removes existing features

- Undo or reopen the original Artifact.
- Use the preservation requirements in Prompt C.
- Open the prebuilt QA-enhanced version if necessary.

## Project grounding appears weak

Ask:

> Identify the Project files and sections that support your previous answer. Remove or label any claim that is not directly supported.

If the answer still lacks grounding, use a prepared response and explain that knowledge curation and evaluation remain necessary.

## Network or service failure

Use the backup screenshots and present the session as a guided walkthrough:

1. Project structure screenshot
2. Grounded answer screenshot
3. Journey Artifact screenshot
4. QA Coverage screenshot

The conceptual lesson remains intact.

---

# 7. Post-session materials

Recommended materials to share:

- The Project-generation prompt
- The Artifact-generation prompt
- The live enhancement prompt
- A screenshot or short recording of the completed Artifact
- The four-slide deck
- A short exercise asking participants to identify a Project and Artifact opportunity in their own work

Suggested exercise:

> Choose a recurring body of work in your team. List the instructions and knowledge that should persist across chats. Then describe one Artifact that could turn that knowledge into a reusable experience.
