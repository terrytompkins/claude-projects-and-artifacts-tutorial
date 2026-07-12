# Presentation Outline

## Session title

# Beyond the Chat

## Subtitle

**Building Reusable Workspaces and Apps with Claude Projects and Artifacts**

## Duration

30 minutes

## Audience

A mixed audience that may include:

- Product managers
- Business analysts
- Developers
- Test engineers
- Architects
- Designers
- AI-curious business users

## Learning objectives

By the end of the session, participants should be able to explain:

1. Why a Claude Project is more useful than repeatedly starting isolated chats.
2. The difference between Project Instructions and Project Knowledge.
3. How multiple chats can reuse the same Project context.
4. How an Artifact turns knowledge and conversation into a reusable interactive experience.
5. How one knowledge base can support product, UX, engineering, and QA perspectives.

---

# 30-minute flow

| Time | Segment | Format |
|---|---|---|
| 0:00–0:03 | Problem and concept | Slides 1–2 |
| 0:03–0:07 | Explore the Pet Care Coach Project | Live Claude Project |
| 0:07–0:12 | Run grounded prompts in two chats | Live Claude chats |
| 0:12–0:19 | Explore the Journey Explorer Artifact | Live Artifact |
| 0:19–0:25 | Add QA Coverage Mode | Live Artifact enhancement |
| 0:25–0:28 | Explain what happened | Slide 3 |
| 0:28–0:30 | Decision guide and takeaway | Slide 4 |

The schedule includes a small amount of buffer. If live generation runs slowly, move directly from the prebuilt Artifact to Slide 3.

---

# Slide 1: Beyond the Chat

## Main message

A normal chat is useful for a question. A Project is useful for a body of work. An Artifact is useful when the output should become something people can use.

## Suggested visual

Three connected boxes:

```text
CHAT
One conversation
One immediate task
        ↓
PROJECT
Shared instructions
Shared knowledge
Multiple conversations
        ↓
ARTIFACT
Document
Visualization
Prototype
Interactive application
```

## Minimal slide text

- Chat: answer a question
- Project: preserve reusable context
- Artifact: create a reusable experience

## Speaker notes

Most people first experience generative AI as a sequence of independent conversations. That works until the work becomes larger than one prompt or one chat.

A Project changes the unit of work. Instead of starting with an empty conversation every time, we create a reusable workspace containing instructions and knowledge.

An Artifact changes the form of the output. Instead of receiving only prose, we can produce a document, diagram, prototype, or interactive application.

---

# Slide 2: What Persists Where?

## Suggested comparison table

| Capability | Normal chat | Claude Project | Artifact |
|---|---:|---:|---:|
| Immediate conversation context | Yes | Yes | Uses creation conversation |
| Shared instructions | No | Yes | Encoded in the result |
| Shared reference files | No | Yes | Can be represented in the result |
| Reused across multiple chats | No | Yes | Shared as a standalone output |
| Interactive user experience | Limited | Limited | Yes |
| Suitable for team knowledge | Limited | Yes | Yes, for a focused experience |

## Main message

The important distinction is not simply “more context.” It is the separation of:

- Conversation history
- Reusable instructions
- Reusable knowledge
- Reusable output

## Speaker notes

Project Instructions define how Claude should behave in this workspace.

Project Knowledge contains the reusable product facts and source material.

Each chat can pursue a different task while drawing on the same shared foundation.

The Artifact is not the Project itself. It is a product created from that context.

## Transition to demo

“Let’s see what this looks like using a small product workspace called Pet Care Coach.”

---

# Live demonstration

The live sequence is described in detail in `05-presenter-runbook.md`.

The central progression should remain visible:

```text
Knowledge files
      ↓
Claude Project
      ↓
Multiple grounded conversations
      ↓
Interactive Artifact
      ↓
Live product enhancement
```

---

# Slide 3: What We Just Built

## Suggested visual

```text
PRODUCT KNOWLEDGE
Overview
Personas
Journey
Requirements
Safety guidance
Demo data
Acceptance criteria
        ↓
PROJECT CONTEXT
Shared across conversations
        ↓
ARTIFACT
Journey Explorer
Home-care interactions
Evidence view
QA coverage
```

## Main message

The Artifact was not created from a single giant prompt alone.

It was created from a structured body of reusable knowledge.

## Suggested talking points

- One Project supported multiple roles.
- The Artifact reused existing identifiers and acceptance criteria.
- Product and safety constraints remained available during iteration.
- A new QA feature was added without recreating the product context.
- The result is still a prototype, but it is a more durable prototype than a one-off chat response.

---

# Slide 4: Which Claude Feature Should I Use?

| Need | Best starting point |
|---|---|
| One question or short task | Normal chat |
| Repeated work using common context | Project |
| A reusable document, visualization, or app | Artifact |
| High-fidelity visual design exploration | Claude Design |
| Source-controlled production software | Claude Code or a development stack |

## Final takeaway

> **Move reusable context into a Project, then turn the most useful results into Artifacts.**

## Closing statement

“The key idea is not that every chat should become an application. The key idea is that once work becomes repeatable, shared, or multi-step, we should stop treating it as an isolated prompt.”

---

# Optional backup slides

These slides should be present in the deck but hidden unless needed.

## Backup slide A: Project contents

List the uploaded files:

- Product overview
- Personas
- Journey
- Features and requirements
- Domain model
- Safety guidance
- Demo data
- Acceptance criteria

## Backup slide B: Completed Artifact screenshot

Use this if the live Artifact does not load.

## Backup slide C: QA Coverage screenshot

Use this if the live enhancement takes too long.

## Backup slide D: Common limitations

- Project knowledge must be curated.
- Shared context does not guarantee perfect grounding.
- Generated interfaces still require review.
- Artifacts are prototypes unless engineered and tested for production.
- Sensitive or regulated information requires appropriate controls.
