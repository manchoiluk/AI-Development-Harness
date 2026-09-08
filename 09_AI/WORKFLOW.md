# Workflow

The AI must follow this fixed flow every time it works.

Each step has a **STOP GATE**. If the gate condition is not met, the AI MUST STOP and either request a Human decision or report the blocker. It must NOT guess, skip, or self-approve.

```text
1. READ                 [Gate 0 — Context Gate]
2. UNDERSTAND           [Gate 1 — Authority Gate]
3. CHECK STATE
4. IDENTIFY TASK        [Gate 2 — Requirement Gate]
5. CHECK SCOPE          [Gate 3 — Scope Gate]
6. PLAN                 [Gate 4 — Plan Gate]
7. IMPLEMENT            [Gate 5 — Implementation Gate]
8. TEST                 [Gate 6 — Test Gate]
9. VERIFY               [Gate 7 — Verification Gate]
10. UPDATE STATE        [Gate 8 — State Gate]
11. REPORT              [Gate 9 — Completion Gate]
```

## READ

Read relevant context:

- PROJECT_CONTRACT.md
- Relevant Product documents
- Relevant Spec documents
- Relevant Design documents
- Current Project State
- Current Task

## Gate 0 — Context Gate

Before starting, the AI MUST confirm all key context above exists.

If any key context is missing:

```text
STOP
```

The AI MUST NOT invent or silently fill in missing context.

## UNDERSTAND

Clarify:

- Current objective
- Input
- Output
- Constraints
- Acceptance Criteria

## Gate 1 — Authority Gate

Confirm the current operation falls within AI authority.

AI MAY:

- Implementation
- Testing
- Debugging
- Refactoring
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

If the task touches any of the latter:

```text
STOP
REQUEST HUMAN DECISION
```

## CHECK STATE

Confirm the current project state.

## IDENTIFY TASK

Confirm the current Task.

When no Task exists:

> Do not create large feature tasks on your own.

## Gate 2 — Requirement Gate

The current Task MUST be traceable to an Approved Requirement.

If the Task cannot be mapped to a Requirement:

```text
STOP
```

The AI MUST NOT create a Requirement on its own.

## CHECK SCOPE

Confirm the change does not exceed scope.

## Gate 3 — Scope Gate

Check the Current Task, Current Requirement, Current Spec, and Current Design.

Confirm the modification does not exceed scope.

Example: Task = implement A. The AI MUST NOT also implement B, C, D merely because they seem easy.

If extra requirements are found:

```text
STOP
REPORT
```

## PLAN

Form a short implementation plan first:

- Objective
- Files to Change
- Implementation Steps
- Tests
- Expected Result

## Gate 4 — Plan Gate

The plan MUST NOT introduce unapproved new product behavior.

## IMPLEMENT

Implement only the current Task.

## Gate 5 — Implementation Gate

Forbidden during implementation:

- Refactoring the whole project on the side
- Upgrading the architecture on the side
- Replacing the tech stack on the side
- Adding features on the side
- Modifying Product on the side
- Modifying Spec on the side

## TEST

Run relevant tests.

## Gate 6 — Test Gate

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

## VERIFY

Check:

- Functional Correctness
- Requirement Compliance
- Spec Compliance
- Scope Compliance
- Product Drift
- Traceability

## Gate 7 — Verification Gate

Verification MUST NOT only check whether the code runs.

It MUST check the six items above.

## UPDATE STATE

Update state.

## Gate 8 — State Gate

Before a Task is complete, the AI MUST update `08_STATE/`:

- Project State
- Implementation State
- Known Issues

These MUST match the actual state.

## REPORT

Report:

```text
Completed
Tests
Verification
Files Changed
Remaining Issues
```

## Gate 9 — Completion Gate

A Task may be marked COMPLETED only when ALL of the following hold:

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
Traceability Complete
+
Verification Complete
+
State Updated
```

Otherwise it MUST NOT be marked complete.
