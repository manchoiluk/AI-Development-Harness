# Phase Template

A Phase is a bounded body of work between approved project states. It is larger than a Task and smaller than the entire product roadmap.

## Phase Identity

```text
Phase ID:
Phase Name:
Status: PLANNED | ACTIVE | FROZEN | COMPLETED
Owner: Human approval / AI execution
```

## Phase Objective

State the single outcome this Phase must establish.

## Entry Conditions

A Phase MUST define:

- Previous Baseline or Project State
- Approved Requirements
- Relevant Specs
- Relevant Design
- Explicit Non-Goals

## Work Breakdown

```text
EPIC
 ├── TASK
 ├── TASK
 └── TASK
```

Each Task MUST have:

- Traceability IDs
- Scope
- Acceptance Criteria
- Test Strategy
- Completion Evidence

## Phase Gates

### Gate A — Entry

Requirements, scope, and source state are known.

### Gate B — Task Readiness

Every executable Task is traceable and has acceptance criteria.

### Gate C — Implementation

Only approved Tasks are implemented.

### Gate D — Regression

Previous Baseline behavior remains valid unless an approved Change says otherwise.

### Gate E — Phase Verification

All required Tasks are completed, tests pass, traceability is complete, and project state is updated.

### Gate F — Human Acceptance

Human accepts the resulting project state before a new Baseline is declared.

## Phase Completion Record

Record:

- Completed Tasks
- Test Results
- Verification Results
- Known Limitations
- Compatibility Notes
- Deferred Work
- Resulting Project State
- Whether a new Baseline was accepted
