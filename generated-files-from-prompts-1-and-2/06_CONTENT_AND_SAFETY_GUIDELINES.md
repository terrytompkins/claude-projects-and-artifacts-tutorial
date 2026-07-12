# Pet Care Coach — Content and Safety Guidelines

*Applies to all owner-facing and clinic-facing content in the prototype. The canonical Jordan/Bailey case and all clinical details are fictional demonstration material.*

## Voice and tone

Calm, warm, and direct. Sound like a well-organized front-desk assistant, not a medical authority. Avoid alarming or overly casual language; avoid clinical jargon unless immediately explained.

## Plain-language principles

- Prefer short sentences and everyday words over medical terminology.
- Explain any necessary clinical term the first time it appears (e.g., "dehydration — losing more fluid than you're taking in").
- Lead with the action the owner needs to take, then the explanation.

## Required uncertainty language

When presenting AI-generated content, use phrasing that keeps the system's role clear, such as "Based on what you described, this may need a same-day visit" rather than "You have..." Never use definitive diagnostic language ("Bailey has gastrointestinal irritation") outside of clinician-entered, clinician-approved content.

## Emergency and escalation presentation

- Escalation messaging must be visually distinct (e.g., a clearly marked banner), appear immediately, and never be buried below other content.
- Always pair an escalation flag with one explicit next action ("Contact Pine Ridge Veterinary Clinic now" or "Request a same-day appointment").
- Never phrase escalation guidance as a guarantee ("this is definitely not an emergency"). Use conservative, action-oriented phrasing instead.

## Prohibited content

- No medication dosages, frequencies, or administration instructions beyond "per the clinic label."
- No invented diagnoses, prognoses, or treatment recommendations.
- No home remedies that were not explicitly provided by the clinic.
- No content that could be mistaken for a real clinic's live medical advice.

## How to label AI-generated summaries

Prefix or tag with: **"AI-generated summary — not a diagnosis."** Applies to the TriageSummary, the structured clinic summary, and follow-up answers where `answeredBy` is `ai`.

## How to label clinic-record information

Prefix or tag with: **"From the clinic record."** Applies to Appointment, ClinicVisit, and DiagnosticResult data as entered by clinic staff.

## How to label veterinarian-approved instructions

Prefix or tag with: **"Veterinarian-approved."** Applies to the CarePlan and every CareTask description.

## Source hierarchy

From highest to lowest authority:

1. **Veterinarian-approved instructions** (the CarePlan and CareTasks) — always authoritative.
2. **Clinic-record information** (ClinicVisit notes, DiagnosticResult findings) — factual record from the visit.
3. **AI-generated summaries and explanations** (TriageSummary, structured clinic summary, diagnostic-result explanations, follow-up answers) — supportive, always subordinate to 1 and 2.
4. **General educational information** — background context only, not specific to this episode.

If any AI-generated content appears to conflict with the veterinarian-approved plan, the interface must defer to the plan and flag the conflict rather than silently reconciling it.

## Accessibility guidance

- Never rely on color alone to convey source/approval labeling — pair color with an icon and text label.
- Ensure all interactive elements (task checkboxes, escalation banners, follow-up question input) are reachable and operable via keyboard.
- Use sufficient contrast and readable font sizes for users who may be viewing content while stressed or distracted.
- Provide descriptive alt text or labels for any icons used in the labeling taxonomy.

## Privacy reminders

- Treat all owner and pet information as sensitive; do not surface it outside the relevant owner/clinic context.
- This prototype uses fictional data only — no real personal or health information should ever be entered into it.
- Avoid placing any identifying information in URLs or logs within the prototype's design.

## Example acceptable messages

- "Based on what you described, a same-day visit is a good idea. Contact Pine Ridge Veterinary Clinic or request an appointment below. (AI-generated summary — not a diagnosis.)"
- "Veterinarian-approved: Offer small meals according to Dr. Chen's diet instructions for today."
- "From the clinic record: Mild dehydration was observed during today's exam."

## Example unacceptable messages, with corrected alternatives

- Unacceptable: "Bailey has gastroenteritis and needs anti-nausea medicine twice a day."
  Corrected: "Veterinarian-approved: Give the anti-nausea medication according to the clinic label." (No diagnosis stated as fact by the AI; no dosage.)
- Unacceptable: "This is definitely not an emergency, don't worry."
  Corrected: "Based on what you described, this doesn't appear urgent, but please contact the clinic right away if vomiting continues or Bailey seems worse. (AI-generated summary — not a diagnosis.)"
- Unacceptable: "Try giving Bailey some ginger to settle her stomach."
  Corrected: "Home remedies aren't part of Bailey's veterinarian-approved plan. Please check with Pine Ridge Veterinary Clinic before trying anything not listed in the care plan."
