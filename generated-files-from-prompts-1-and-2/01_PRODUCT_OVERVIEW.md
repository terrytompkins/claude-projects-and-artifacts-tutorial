# Pet Care Coach — Product Overview

> **This is an educational prototype.** Pet Care Coach demonstrates generative AI product-design techniques for a classroom setting. It is not a real product, does not diagnose conditions, and does not replace a veterinarian. All health scenarios, including the canonical case of Bailey and Jordan Lee, are fictional demonstration material.

## Product vision

Pet owners leave the vet's office with a lot to remember and no easy way to check whether they're doing the right thing at home. Pet Care Coach envisions an assistant that helps owners describe a concern clearly, understand what happens next, and confidently follow the veterinarian-approved care plan afterward — without ever standing in for the veterinarian's judgment.

## Problem statement

Owners often struggle in three moments: deciding whether a symptom needs a vet visit, explaining the concern efficiently once they're at the clinic, and remembering and correctly following care instructions after they get home. Existing tools either offer generic, ungrounded symptom information or provide no structured way to carry information from the AI conversation into the clinic and back out again as a care plan.

## Target users

- **Pet owners** (canonical example: Jordan Lee) who want plain-language guidance and a clear checklist of next actions.
- **Veterinarians** (canonical example: Dr. Maya Chen) who need concise, accurate intake information and want AI content clearly separated from their own clinical judgment.
- **Veterinary technicians** (canonical example: Alex Rivera) who triage incoming information and support the visit.
- **Product managers / QA reviewers** (canonical example: Sam Patel) who need to validate that the prototype behaves safely and meets requirements.

## Value proposition

Pet Care Coach turns a stressful, fragmented experience — vague worry, rushed clinic visit, forgotten instructions — into a guided, well-labeled journey where the owner always knows what's general information, what's from the pet's clinic record, and what's officially approved by the veterinarian.

## Goals

- Help owners describe symptoms clearly and completely before a visit.
- Surface urgent situations early and point owners toward appropriate next steps.
- Reduce repeated intake work for clinic staff via a structured summary.
- Make post-visit care instructions easy to find, understand, and track.
- Keep AI-generated content clearly and consistently distinguished from clinician-approved content.

## Non-goals

- Pet Care Coach does not diagnose medical conditions.
- Pet Care Coach does not prescribe or calculate medication dosages.
- Pet Care Coach does not replace emergency veterinary services.
- Pet Care Coach does not attempt real-time integration with live clinic systems in this prototype.

## Major capabilities

1. Guided symptom conversation with safety-aware clarifying questions.
2. Escalation messaging that flags when urgent care may be needed.
3. Structured, clinic-ready conversation summaries.
4. Appointment request and scheduling for non-emergency cases.
5. A clinic-facing review view for staff.
6. Plain-language explanation of clinician-recorded diagnostic results.
7. A home-care task checklist tied to the vet-approved plan.
8. A follow-up question assistant for the recovery period.
9. Adherence and progress tracking visible to clinic staff.
10. Consistent source and approval labeling across the whole experience.
11. A product/QA evidence view for validating the prototype.

## Success measures

For a classroom prototype, success is measured qualitatively:

- Every AI-generated statement is clearly labeled and distinguishable from clinician-approved content.
- The full journey (concern → follow-up) can be demonstrated end to end using the canonical Jordan/Bailey case.
- Reviewers (e.g., Sam Patel) can trace every feature to at least one acceptance criterion.
- No medication dosage or invented diagnosis appears anywhere in the experience.

## Product principles

- **Never diagnose, never dose.** The system explains and organizes; the veterinarian decides.
- **Label everything.** Every piece of content states whether it's general information, clinic-record data, an AI-generated summary, or veterinarian-approved.
- **Escalate conservatively.** When uncertain, guide the owner toward professional contact rather than reassurance.
- **Reduce repetition.** Information the owner already gave should not need to be re-typed for clinic staff.
- **Plain language first.** Explanations should be understandable without medical training.

## Current prototype scope

The prototype covers the single canonical case of Jordan Lee and Bailey through Pine Ridge Veterinary Clinic, across all seven journey stages, using static/demo data rather than live systems.

## Explicit assumptions

- The prototype uses one owner, one pet, and one clinic for demonstration purposes.
- "Scheduling" in this prototype represents a request/confirmation flow, not a live calendar integration.
- All names, dates, and clinical details are fictional and created solely for this class.

## Risks and limitations

- Risk that an AI-generated explanation could be mistaken for a diagnosis if labeling is inconsistent.
- Risk that escalation logic, if oversimplified for a demo, could imply a level of clinical reliability the prototype does not have.
- Limitation: no real clinic integration, authentication, or payment handling exists in this prototype.
- Limitation: the data model supports one pet per episode; multi-pet households are out of scope.
