# AI Development Harness Template

This repository is a template.
It contains no product implementation.

## What This Is

A reusable, project-agnostic scaffold for building software with an AI coding agent.
It fixes the engineering flow:

```text
Human Product Owner
        ↓
Product
        ↓
Spec
        ↓
Design
        ↓
Task
        ↓
Implementation
        ↓
Test
        ↓
Verification
        ↓
Project State
```

## Suitable Projects

This template can be copied for:

- WeChat Mini Programs
- Games
- Web applications
- Desktop applications
- Mobile applications
- Backend services
- AI tools
- Other software projects

No specific technology stack is assumed or included.

## How To Copy

1. Copy this repository (without any product code) to a new project location.
2. Rename the root folder to your project name.
3. Keep the numbered directory structure intact.
4. Fill in `[PLACEHOLDER]` content as the project progresses.
5. Do not add product code into this harness. Product code lives in a separate implementation location.

## What Each Directory Owns

| Directory | Responsibility |
|-----------|----------------|
| `00_PRODUCT/` | What does the human actually want? Vision, PRD, Roadmap, Non-Goals. |
| `01_SPEC/` | What behavior and rules must the product have? The product behavior contract. |
| `02_DESIGN/` | What engineering structure implements the Spec? Design must not redefine product needs. |
| `03_DECISIONS/` | Record of significant decisions that have been made. |
| `04_CHANGES/` | Approved changes and pending change proposals. |
| `05_TASKS/` | What should the AI do next? Backlog, active, completed. |
| `06_TESTS/` | How do we prove the implementation is correct? |
| `07_VERIFICATION/` | How do we prove the Task is done and there is no product drift? |
| `08_STATE/` | What is the project's current state, exactly? |
| `09_AI/` | How the AI should work and what its boundaries are. |
| `99_FUTURE/` | What might we want later? Never the current task. |

## V0.2 Governance

This template adds four enforceable capabilities on top of the base flow:

- **STOP GATES** — every workflow step has a hard blocking condition (`09_AI/WORKFLOW.md`).
- **TRACEABILITY** — Requirement → Spec → Design → Task → Test → Verification, forward and reverse (`05_TASKS/TRACEABILITY.md`).
- **STATE MACHINE** — explicit Task lifecycle with forbidden transitions and a `BLOCKED` state (`08_STATE/STATE_MACHINE.md`).
- **AUTHORITY MATRIX** — Human authorizes, AI executes within approval (`PROJECT_CONTRACT.md`).

V0.2 is governance + documentation + structure. It is not a software system.

## AI Basic Workflow

Each time the AI works, it follows a fixed flow:

```text
1. READ
2. UNDERSTAND
3. CHECK STATE
4. IDENTIFY TASK
5. CHECK SCOPE
6. PLAN
7. IMPLEMENT
8. TEST
9. VERIFY
10. UPDATE STATE
11. REPORT
```

See `09_AI/WORKFLOW.md` for the full rules.

## How To Start A New Project

1. Copy the template.
2. Fill `00_PRODUCT/VISION.md` and `00_PRODUCT/PRD.md` (Human-owned).
3. Build the Spec in `01_SPEC/`.
4. Design the structure in `02_DESIGN/`.
5. Break work into Tasks in `05_TASKS/`.
6. Let the AI execute Tasks, run Tests, and perform Verification.
7. Keep `08_STATE/` up to date at all times.
