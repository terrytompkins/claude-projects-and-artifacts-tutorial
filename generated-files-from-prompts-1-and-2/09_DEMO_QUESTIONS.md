# Pet Care Coach — Demonstration Runbook

*For use with the "Pet Care Coach Product Workspace" Claude Project.*

## Normal-chat comparison prompt

Run this in a **normal Claude conversation with no project knowledge attached**, to contrast with the grounded prompts below:

> "Propose a product experience for an AI assistant that helps pet owners understand and follow veterinary care instructions before and after a clinic visit. Include key features and a sample user journey."

**What it demonstrates:** Without project knowledge, Claude will invent its own names, IDs, features, and journey — useful for showing the class how much specific, consistent detail a Project grounds automatically versus a normal chat.

---

## Project-grounded prompts

### 1. Executive summary

**Prompt:** "Summarize Pet Care Coach for an executive audience in under 150 words."

- **What it demonstrates:** Concise synthesis grounded in `01_PRODUCT_OVERVIEW.md`.
- **Expected evidence:** References to the vision, target users, and non-goals (no diagnosis, no dosages) from `01_PRODUCT_OVERVIEW.md`.
- **Likely follow-up prompt:** "Now write the same summary for a room of veterinarians instead of executives."

### 2. Jordan and Bailey's journey

**Prompt:** "Walk me through Jordan and Bailey's journey from noticing a concern to the follow-up visit."

- **What it demonstrates:** Claude pulling a full, ordered narrative from `03_END_TO_END_JOURNEY.md` using exact stage IDs and the canonical case.
- **Expected evidence:** All seven stage IDs in order, referencing episode `episode-bailey-2026-07` and citing `03_END_TO_END_JOURNEY.md`.
- **Likely follow-up prompt:** "Which of those stages carries the most safety risk, and why?"

### 3. Most important product risk

**Prompt:** "What is the single most important product risk in Pet Care Coach right now, and what would you do about it?"

- **What it demonstrates:** Claude distinguishing documented facts (risks in `01_PRODUCT_OVERVIEW.md` and `03_END_TO_END_JOURNEY.md`) from its own proposed mitigation.
- **Expected evidence:** Citation of a specific risk (e.g., AI-generated content being mistaken for a diagnosis) plus a clearly labeled proposal.
- **Likely follow-up prompt:** "Turn that mitigation into an acceptance criterion using our AC ID format."

### 4. QA test plan for home-care

**Prompt:** "Produce a QA test plan for the home-care journey stage, grounded in our acceptance criteria."

- **What it demonstrates:** Cross-referencing `04_FEATURES_AND_REQUIREMENTS.md`, `08_ACCEPTANCE_CRITERIA.md`, and the `home-care` stage.
- **Expected evidence:** Coverage of F-006, F-007, and F-010, citing specific AC IDs such as `AC-F007-01` and `AC-F010-02`.
- **Likely follow-up prompt:** "Which of those test cases would be hardest to automate, and why?"

### 5. Comparing persona needs

**Prompt:** "Compare what Jordan, Dr. Chen, and Alex each need from the product, and where their needs conflict."

- **What it demonstrates:** Synthesis across `02_PERSONAS.md` without inventing new persona traits.
- **Expected evidence:** Specific responsibilities/goals/trust concerns per persona, plus an honest tension (e.g., Jordan wants reassurance; Dr. Chen wants strict separation of AI content from her clinical judgment).
- **Likely follow-up prompt:** "Design one interface element that resolves that conflict."

### 6. Sourcing every significant claim

**Prompt:** "List the significant factual claims in `01_PRODUCT_OVERVIEW.md` and tell me which file and section supports each one."

- **What it demonstrates:** The citation behavior required by `00_PROJECT_INSTRUCTIONS.md`.
- **Expected evidence:** Each claim paired with a filename/section citation, or explicitly flagged as unsupported if it can't be traced.
- **Likely follow-up prompt:** "Are there any claims in that file that aren't supported anywhere else in the project? Flag them as contradictions or gaps."

### 7. Preparing to build an interactive Artifact

**Prompt:** "Before we build the React Artifact, summarize the exact data shape, features, and labeling rules it needs to respect."

- **What it demonstrates:** Claude translating documentation into an implementation-ready brief, sourced from `05_DOMAIN_AND_DATA_MODEL.md`, `04_FEATURES_AND_REQUIREMENTS.md`, and `06_CONTENT_AND_SAFETY_GUIDELINES.md`.
- **Expected evidence:** Reference to the CareEpisode JSON shape, the source/approval labeling taxonomy, and the MVP feature list (F-001–F-005, F-007, F-010).
- **Likely follow-up prompt:** "Now build that as a single-file React Artifact using the sample data in `07_SAMPLE_DEMO_DATA.json`."

---

## Demo facilitation notes

**Best to run live:**
- Prompt 2 (Jordan and Bailey's journey) and Prompt 5 (persona comparison) — visually engaging, easy for a mixed audience to follow, and low risk of a long generation time.
- The normal-chat comparison prompt, run first, to set up contrast before showing the grounded prompts.

**Best generated in advance:**
- Prompt 4 (QA test plan) and Prompt 7 (Artifact-prep brief) — longer, more detailed outputs that are better shown pre-generated and then briefly re-run live for authenticity.

**What to point out to a mixed audience:**
- How consistently Claude reuses exact IDs (episode, stage, feature, task) instead of drifting between synonyms.
- How citations point back to specific files instead of vague general knowledge.
- How safety boundaries (no dosages, fictional labeling, source hierarchy) hold up even when directly asked about clinical details.

**Fallback approach if generation takes too long:**
- Have Prompt 2 and Prompt 6 pre-generated as backup screenshots or a secondary tab.
- If live generation stalls, switch to a pre-generated response and note that you're showing a captured run for time, then optionally re-run it after class.
