# Pet Care Coach Knowledge Bundle — README

This bundle is a fictional, educational knowledge set for demonstrating Claude Projects and Artifacts in class. It describes **Pet Care Coach**, a prototype that helps pet owners understand and follow veterinary care instructions before and after a clinic visit. It does not diagnose conditions or replace a veterinarian. All health scenarios, including the canonical case of Jordan Lee and Bailey, are fictional demonstration material.

## What the bundle contains

| File | Contents |
|---|---|
| `00_PROJECT_INSTRUCTIONS.md` | Copy-ready text for the Project Instructions field |
| `01_PRODUCT_OVERVIEW.md` | Vision, goals, non-goals, capabilities, risks |
| `02_PERSONAS.md` | Four personas: Jordan, Dr. Chen, Alex, Sam |
| `03_END_TO_END_JOURNEY.md` | Seven-stage journey, handoffs, flowchart, risks |
| `04_FEATURES_AND_REQUIREMENTS.md` | Features F-001–F-011, MVP grouping, traceability |
| `05_DOMAIN_AND_DATA_MODEL.md` | Entities, ER diagram, sample JSON shape |
| `06_CONTENT_AND_SAFETY_GUIDELINES.md` | Voice, labeling rules, source hierarchy, examples |
| `07_SAMPLE_DEMO_DATA.json` | Complete, valid JSON demo dataset |
| `08_ACCEPTANCE_CRITERIA.md` | 29 acceptance criteria with Given/When/Then and traceability |
| `09_DEMO_QUESTIONS.md` | Demonstration runbook and facilitation notes |
| `README.md` | This file |

## How to create the Claude Project

1. In Claude, create a new Project named **Pet Care Coach Product Workspace**.
2. Open **Set project instructions**.
3. Copy the entire contents of `00_PROJECT_INSTRUCTIONS.md` into that field.
4. Upload the other ten files (`01_PRODUCT_OVERVIEW.md` through `09_DEMO_QUESTIONS.md`, plus this `README.md` if desired) as Project Knowledge.

## Which file to copy into Project Instructions

`00_PROJECT_INSTRUCTIONS.md` — and only that file. The other files belong in Project Knowledge, not the instructions field.

## Which files to upload as Project Knowledge

All files except `00_PROJECT_INSTRUCTIONS.md`:
`01_PRODUCT_OVERVIEW.md`, `02_PERSONAS.md`, `03_END_TO_END_JOURNEY.md`, `04_FEATURES_AND_REQUIREMENTS.md`, `05_DOMAIN_AND_DATA_MODEL.md`, `06_CONTENT_AND_SAFETY_GUIDELINES.md`, `07_SAMPLE_DEMO_DATA.json`, `08_ACCEPTANCE_CRITERIA.md`, `09_DEMO_QUESTIONS.md`, and this `README.md`.

## How to verify the Project is using its knowledge

Ask a question whose answer only exists in the files, and confirm Claude cites the filename, for example:

> "What is Bailey's appointment date and time, and which file did you get that from?"

A correctly configured Project should answer "July 15, 2026 at 2:30 PM" and cite `07_SAMPLE_DEMO_DATA.json` or `04_FEATURES_AND_REQUIREMENTS.md`/`03_END_TO_END_JOURNEY.md`, not answer from general knowledge or invent a different date.

## Recommended order for the live demonstration

1. Normal-chat comparison prompt (no project knowledge) — see `09_DEMO_QUESTIONS.md`.
2. Executive summary (Prompt 1).
3. Jordan and Bailey's journey (Prompt 2).
4. Persona comparison (Prompt 5).
5. Sourcing every significant claim (Prompt 6).
6. QA test plan or Artifact-prep brief (Prompt 4 or 7), depending on remaining time.
7. If time allows, generate the interactive React Artifact live, using `05_DOMAIN_AND_DATA_MODEL.md` and `07_SAMPLE_DEMO_DATA.json` as the grounding source.

## Authoritative sources by topic

| Topic | Authoritative file |
|---|---|
| Product scope and vision | `01_PRODUCT_OVERVIEW.md` |
| Journey and stage definitions | `03_END_TO_END_JOURNEY.md` |
| Safety, labeling, and tone | `06_CONTENT_AND_SAFETY_GUIDELINES.md` |
| Data structure | `05_DOMAIN_AND_DATA_MODEL.md` and `07_SAMPLE_DEMO_DATA.json` |
| Acceptance criteria | `08_ACCEPTANCE_CRITERIA.md` |

## Five-minute pre-class verification checklist

1. Confirm the Project was created with the name **Pet Care Coach Product Workspace**.
2. Confirm `00_PROJECT_INSTRUCTIONS.md` content is in the Project Instructions field (not uploaded as Knowledge).
3. Confirm all ten remaining files are uploaded as Project Knowledge.
4. Ask the verification question above and confirm the date, citation, and lack of invented details.
5. Ask "What are Bailey's six home-care tasks?" and confirm all six exact task IDs/descriptions appear and are labeled "veterinarian-approved."
6. Ask "Does Pet Care Coach ever provide medication dosages?" and confirm Claude answers no and explains why.

## File consistency matrix

| Element | 00 | 01 | 02 | 03 | 04 | 05 | 06 | 07 | 08 | 09 |
|---|---|---|---|---|---|---|---|---|---|---|
| Canonical case (Jordan/Bailey) | — | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| Seven journey-stage IDs | — | ✔ | ✔ | ✔ | ✔ | ✔ | — | ✔ | ✔ | ✔ |
| Feature IDs F-001–F-011 | — | ✔ | ✔ | ✔ | ✔ | — | — | — | ✔ | ✔ |
| Six care-task IDs | — | — | — | — | ✔ | ✔ | — | ✔ | — | — |
| Source/approval labeling taxonomy | ✔ | — | — | — | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| Acceptance-criteria IDs | — | — | — | — | — | — | — | ✔ (subset) | ✔ (full) | — |
| "Fictional demonstration data" labeling | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
