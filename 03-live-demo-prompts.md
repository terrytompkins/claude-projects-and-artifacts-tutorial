# Live Demo Prompts

Keep this file open during the session.

The recommended sequence is:

1. Run **Prompt A** in one Project chat.
2. Run **Prompt B** in a second Project chat.
3. Open the prebuilt Artifact.
4. Demonstrate its existing interactions.
5. Run **Prompt C** to add QA Coverage Mode.
6. Use the repair prompt only if necessary.

---

## Prompt A: Test the Project knowledge

Based only on this Project’s uploaded knowledge, explain Jordan and Bailey’s experience from the initial concern through at-home follow-up.

Use a compact table with these columns:

- Journey stage
- Jordan’s goal
- Pet Care Coach behavior
- Human responsibility
- Primary safety consideration
- Source filename

Use the exact canonical journey-stage names and IDs.

Do not introduce clinical facts that are absent from the Project. After the table, identify one product risk that would be easy to miss if the feature were designed from a single chat rather than from the complete Project knowledge.

### What to point out

- Claude uses the exact journey stages from Project Knowledge.
- The answer includes product, human-responsibility, and safety perspectives.
- The source filenames show that the answer is grounded in reusable context.
- This chat does not need the background copied into its immediate conversation.

---

## Prompt B: Show cross-functional reuse

Using the same Project knowledge, explain how the `home-care` stage should be viewed differently by:

1. Jordan Lee
2. Dr. Maya Chen
3. Alex Rivera
4. Sam Patel

For each person provide:

- Their goal
- The information they need
- The action they can take
- Their primary trust or safety concern
- The relevant feature IDs
- The relevant acceptance-criteria IDs
- The Project files supporting the answer

End by explaining which information is owner-provided, AI-generated, clinic-record information, and veterinarian-approved.

### What to point out

- The same Project supports multiple roles without creating separate knowledge stores.
- Claude can shift perspective while preserving shared facts.
- Stable feature and acceptance-criteria IDs make the answer useful to product and QA teams.
- Source and approval distinctions reduce the chance of treating AI output as authoritative clinical guidance.

---

## Prompt C: Live Artifact enhancement

Update the existing **Pet Care Coach Journey Explorer** Artifact. Preserve its current functionality, visual language, responsive behavior, sample records, source badges, and existing state interactions.

Add a new capability named:

# QA Coverage Mode

This must be an enhancement to the existing Artifact, not a replacement application.

## Required behavior

Add a `QA Coverage` toggle that is visible when the `Product & QA` perspective is selected.

When QA Coverage Mode is enabled:

1. Display the acceptance criteria related to the currently selected journey stage.
2. Show each criterion’s:
   - Acceptance-criteria ID
   - Related feature ID
   - Brief criterion text
   - Scenario type
   - Coverage status
3. Use three fictional coverage states:
   - Covered
   - Partial
   - Not covered
4. Include a compact summary showing:
   - Total criteria for the stage
   - Covered count
   - Partial count
   - Not-covered count
5. Allow filtering by coverage state.
6. Allow selecting a criterion to reveal its Given/When/Then scenario.
7. Include the supporting Project filename.
8. Use only acceptance criteria contained in `08_ACCEPTANCE_CRITERIA.md`.
9. Do not generate new criteria merely to fill the interface.

Add a small teaching note:

**This view demonstrates that the same Project knowledge can support product, user-experience, and testing workflows.**

## Preservation requirements

Do not remove or break:

- Perspective selection
- Journey-stage navigation
- Home-care task completion
- Progress calculation
- Evidence filters
- Follow-up examples
- Reset behavior
- Accessibility features
- Source and approval badges

Reset must also restore QA Coverage Mode and its filters to their initial state.

Verify all controls after making the change. Make the smallest coherent code changes needed and return the updated working Artifact.

### What to point out while Claude works

- The enhancement request refers to the existing Artifact rather than starting over.
- The Project already contains the acceptance criteria needed for the new feature.
- Product context and QA evidence are being reused without another upload.
- The user can direct a meaningful product change in ordinary language.

---

## Optional follow-up: Make the enhancement more presentable

Use this only if the first QA Coverage implementation works but is visually dense.

Refine the new QA Coverage Mode without changing its underlying data, behavior, or acceptance-criteria mappings.

Improve it for presentation on a projected screen:

- Increase legibility.
- Reduce visual density.
- Make the summary counts easy to scan.
- Make the selected coverage filter unmistakable.
- Keep the Given/When/Then details collapsed until selected.
- Preserve keyboard accessibility.
- Preserve the existing visual language of the Artifact.
- Do not remove any existing functionality.

Return the updated Artifact directly.

---

## Emergency repair prompt

Use this only if the Artifact preview fails.

Review the current Artifact for runtime errors, missing references, unsupported imports, invalid data access, and state initialization problems.

Repair the existing Artifact without redesigning it or removing features.

Requirements:

- Use only React and standard browser capabilities.
- Remove unsupported dependencies.
- Preserve all visible functionality where possible.
- Use safe fallbacks when Project data is absent.
- Confirm that every mapped collection is an array before iterating.
- Confirm that selected IDs resolve to valid records.
- Confirm that reset initializes every state variable.
- Ensure the Artifact renders immediately in preview.

Return the repaired Artifact directly.

---

## Fallback prompt: Explain the enhancement without generating it live

Use this if the live generation would consume too much time.

Using the existing Artifact and Project Knowledge, describe exactly how QA Coverage Mode would be added.

Provide:

- The new user interaction
- The Project files it would use
- The data mappings required
- The state changes required
- The acceptance criteria that would be displayed
- The existing functionality that must be preserved

Keep the explanation under 500 words and structure it for a mixed technical and nontechnical audience.
