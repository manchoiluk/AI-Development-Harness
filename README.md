# AI Development Harness Template

This repository is a reusable, project-agnostic scaffold for building software with an AI coding agent.

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
Phase
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
        ↓
Baseline
```

## Core Principle

The Human owns **direction and approval**. The AI owns **execution within approved scope**.

The Harness is designed to prevent a capable coding agent from silently changing the product, expanding scope, or redefining a working foundation while implementing new work.

## Baseline + Phase Governance

The Harness supports two additional control layers:

- **BASELINE FREEZE** — a Human-accepted working state becomes a protected regression reference.
- **PHASE GOVERNANCE** — work is organized into bounded Phases containing traceable Tasks with entry/exit gates.
- **EVIDENCE / COMPATIBILITY** — external-system behavior is recorded as VERIFIED, OBSERVED, INFERRED, or UNKNOWN, with version-specific compatibility notes when applicable.

See:

- `09_AI/BASELINE_FREEZE.md`
- `09_AI/EVIDENCE_AND_COMPATIBILITY.md`
- `05_TASKS/PHASE_TEMPLATE.md`
- `05_TASKS/TASK_EXECUTION_TEMPLATE.md`
- `09_AI/WORKFLOW.md`

## Suitable Projects

This template can be copied for:

- WeChat Mini Programs
- Games
- Web applications
- Desktop applications
- Mobile applications
- Backend services
- AI tools
- SDKs and developer infrastructure
- Other software projects

No specific technology stack is assumed or included.

## How To Copy

1. Copy this repository (without product code) to a new project location.
2. Rename the root folder to your project name.
3. Keep the numbered directory structure intact.
4. Fill in `[PLACEHOLDER]` content as the project progresses.
5. Do not add product implementation into the Harness. Product code belongs in the implementation project.

## Directory Ownership

| Directory | Responsibility |
|-----------|----------------|
| `00_PRODUCT/` | What does the human actually want? Vision, PRD, Roadmap, Non-Goals. |
| `01_SPEC/` | What behavior and rules must the product have? |
| `02_DESIGN/` | What engineering structure implements the Spec? |
| `03_DECISIONS/` | Significant approved decisions. |
| `04_CHANGES/` | Approved changes and pending change proposals. |
| `05_TASKS/` | Phase planning, backlog, active and completed Tasks, traceability. |
| `06_TESTS/` | How do we prove the implementation is correct? |
| `07_VERIFICATION/` | How do we prove the Task is done and there is no product drift? |
| `08_STATE/` | What is the project's current state, exactly? |
| `09_AI/` | How the AI should work and what its boundaries are. |
| `99_FUTURE/` | What might we want later? Never the current task. |

## V0.3 Governance

The Harness now combines:

- **STOP GATES** — every workflow step has a blocking condition.
- **TRACEABILITY** — Requirement → Spec → Design → Task → Test → Verification.
- **STATE MACHINE** — explicit Task lifecycle with forbidden transitions and `BLOCKED`.
- **AUTHORITY MATRIX** — Human authorizes; AI executes within approval.
- **BASELINE FREEZE** — accepted project states become regression references.
- **PHASE GATES** — bounded groups of Tasks have explicit entry, regression, and acceptance gates.
- **EVIDENCE CLASSES** — external behavior cannot become contract merely because it was inferred.

V0.3 is still governance + documentation + structure. It is not a software system.

## AI Basic Workflow

Each time the AI works:

```text
1. READ BASELINE / CONTEXT
2. READ
3. UNDERSTAND
4. CHECK STATE
5. IDENTIFY TASK
6. CHECK SCOPE
7. PLAN
8. IMPLEMENT
9. TEST
10. VERIFY
11. UPDATE STATE
12. REPORT
```

If a STOP GATE fails, the AI stops and requests a Human decision or reports the blocker.

## How To Start A New Project

1. Copy the template.
2. Fill `00_PRODUCT/VISION.md` and `00_PRODUCT/PRD.md` (Human-owned).
3. Build the Spec in `01_SPEC/`.
4. Design the structure in `02_DESIGN/`.
5. Define the first Phase and its Tasks.
6. Let the AI execute only Tasks that are `READY` and traceable.
7. Run Tests and Verification.
8. Update `08_STATE/`.
9. When a milestone is accepted, create a Baseline record and freeze it.
10. Start the next Phase from that Baseline.
