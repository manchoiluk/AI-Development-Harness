# Workflow

The AI must follow this fixed flow every time it works.

Each step has a **STOP GATE**. If the gate condition is not met, the AI MUST STOP and either request a Human decision or report the blocker. It must NOT guess, skip, or self-approve.

```text
0. READ BASELINE / CONTEXT [Gate 0]
1. READ                [Gate 1]
2. UNDERSTAND          [Gate 2]
3. CHECK STATE         [Gate 3]
4. IDENTIFY TASK      [Gate 4]
5. CHECK SCOPE         [Gate 5]
6. PLAN                [Gate 6]
7. IMPLEMENT           [Gate 7]
8. TEST                [Gate 8]
9. VERIFY              [Gate 9]
10. UPDATE STATE       [Gate 10]
11. REPORT             [Gate 11]
```

## 0. READ BASELINE / CONTEXT

Before touching code, determine:

- Current frozen Baseline, if one exists
- Current Phase
- Current Project State
- Relevant Product documents
- Relevant Spec documents
- Relevant Design documents
- Current Task
- Relevant compatibility/evidence records

### Gate 0 — Context Gate

The AI MUST know what state it is changing and what contract must remain stable.

If the current Baseline, Task, or required context is missing:

```text
STOP
```

The AI MUST NOT invent missing context.

## 1. READ

Read relevant context:

- PROJECT_CONTRACT.md
- Relevant Product documents
- Relevant Spec documents
- Relevant Design documents
- Current Project State
- Current Task
- Baseline record when present
- Compatibility record when relevant

## Gate 1 — Context Gate

Before starting implementation, all required sources must exist and be consistent.

If sources conflict:

```text
STOP
REPORT CONFLICT
REQUEST HUMAN DECISION
```

## 2. UNDERSTAND

Clarify:

- Current objective
- Input
- Output
- Constraints
- Acceptance Criteria
- Baseline behavior that must remain unchanged
- Evidence required to prove the result

## Gate 2 — Authority Gate

Confirm the current operation falls within AI authority.

AI MAY:

- Implementation
- Testing
- Debugging
- Refactoring within Task scope
- Technical Investigation
- Technical Documentation

AI MUST NOT decide on its own:

- Product Direction
- Product Scope
- Product Behavior
- UX Direction
- Feature Priority
- Requirement Changes
- Locked Design Changes
- Baseline contract changes
- Major architecture direction

If the task touches any of the latter:

```text
STOP
REQUEST HUMAN DECISION
```

## 3. CHECK STATE

Confirm the current project and Task state.

A frozen Baseline is the regression reference until a new Baseline is explicitly accepted.

## Gate 3 — State Gate

Do not start work when the Task is not legally executable under `08_STATE/STATE_MACHINE.md`.

## 4. IDENTIFY TASK

Confirm the current Task.

When no Task exists:

> Do not create large feature Tasks on your own.

A Phase may contain many Tasks, but the AI executes only the explicitly active Task.

## Gate 4 — Requirement Gate

The current Task MUST be traceable to an Approved Requirement.

If the Task cannot be mapped to a Requirement:

```text
STOP
```

The AI MUST NOT create a Requirement on its own.

## 5. CHECK SCOPE

Confirm the change does not exceed scope.

Check:

- Current Task
- Current Requirement
- Current Spec
- Current Design
- Current Baseline
- Current Phase non-goals

## Gate 5 — Scope Gate

Example: Task = implement A. The AI MUST NOT also implement B, C, D merely because they seem easy.

If extra requirements are found:

```text
STOP
REPORT
```

If implementation would change the Baseline contract, use the Change Protocol instead of silently changing it.

## 6. PLAN

Form a short implementation plan first:

- Objective
- Files to Change
- Implementation Steps
- Tests
- Compatibility/evidence work
- Expected Result

## Gate 6 — Plan Gate

The plan MUST NOT introduce unapproved product behavior or silently invalidate the Baseline.

## 7. IMPLEMENT

Implement only the current Task.

## Gate 7 — Implementation Gate

Forbidden during implementation:

- Refactoring the whole project on the side
- Upgrading the architecture on the side
- Replacing the tech stack on the side
- Adding features on the side
- Modifying Product on the side
- Modifying Spec on the side
- Redefining a frozen Baseline

## 8. TEST

Run relevant tests.

If behavior depends on an external system/version, run the relevant compatibility tests or record why they cannot be run.

## Gate 8 — Test Gate

After implementation, the AI MUST run relevant tests.

If tests fail:

```text
DO NOT CLAIM COMPLETE
```

Enter the loop:

```text
DEBUG → TEST
```

If it cannot be fixed:

```text
BLOCKED
```

## 9. VERIFY

Check:

- Functional Correctness
- Requirement Compliance
- Spec Compliance
- Scope Compliance
- Product Drift
- Baseline Regression
- Traceability
- Compatibility/evidence, when applicable

### Gate 9 — Verification Gate

Verification MUST NOT only check whether the code runs.

It MUST check the items above that apply to the Task.

Important external behavior MUST be classified as:

```text
VERIFIED
OBSERVED
INFERRED
UNKNOWN
```

AI MUST NOT turn `INFERRED` or `UNKNOWN` behavior into a stable contract by assumption.

## 10. UPDATE STATE

Update:

- Project State
- Implementation State
- Known Issues
- Phase state when applicable
- Baseline record when a Baseline is being accepted
- Compatibility/evidence records when applicable

## Gate 10 — State Gate

Before a Task is complete, state and documentation MUST match actual implementation and verification results.

## 11. REPORT

Report:

```text
Completed
Tests
Verification
Files Changed
Compatibility / Evidence
Remaining Issues
Deferred Work
State
```

## Gate 11 — Completion Gate

A Task may be marked COMPLETED only when ALL applicable conditions hold:

```text
Implementation Complete
+
Tests Pass
+
Acceptance Criteria Pass
+
Scope Valid
+
No Product Drift
+
No Unapproved Baseline Change
+
Traceability Complete
+
Verification Complete
+
State Updated
+
Compatibility Evidence Recorded (when applicable)
```

## Phase Completion Gate

A Phase is not complete merely because all code Tasks are marked complete.

Before closing a Phase:

1. All required Tasks are COMPLETED.
2. Regression against the previous Baseline passes.
3. Traceability is complete.
4. Known limitations are documented.
5. Deferred work is explicit.
6. Project State is updated.
7. Human accepts the resulting state.

Only then may a new Baseline be declared.
