# Task Execution Template

Copy this template for every AI-executed Task.

## Identity

```text
TASK ID:
PHASE ID:
EPIC ID:
STATUS: BACKLOG | READY | IN_PROGRESS | IMPLEMENTED | TESTING | VERIFIED | COMPLETED | BLOCKED
```

## Traceability

```text
Requirement:
Spec:
Design:
Baseline:
```

## Objective

One sentence describing the exact engineering outcome.

## Scope

### Allowed

- Files/directories that may change
- APIs/models that may change
- Tests that may be added

### Forbidden

- Unrelated features
- Product behavior changes
- Architecture changes outside the Task
- Spec changes without approval
- Baseline contract changes without Change approval

## Acceptance Criteria

Use objective, testable statements.

```text
[ ] AC-1
[ ] AC-2
[ ] AC-3
```

## Evidence Requirements

When behavior depends on an external system, record the evidence source and classify each important fact as:

- VERIFIED — directly tested or documented
- OBSERVED — seen during execution but not fully characterized
- INFERRED — reasonable interpretation, not proven
- UNKNOWN — not established

Never promote INFERRED or UNKNOWN behavior to a contract without verification or Human approval.

## Compatibility

If an external protocol/version matters, record:

```text
System:
Version:
Native capability:
Emulated capability:
Unsupported capability:
Evidence:
```

## Implementation Plan

1. Inspect current implementation.
2. Identify the smallest required change.
3. Implement only the approved scope.
4. Add/update tests.
5. Run verification.
6. Update state and documentation.

## Completion Evidence

```text
Files changed:
Tests run:
Test results:
Verification:
Known issues:
Deferred work:
```

## Completion Gate

A Task is COMPLETED only when:

- Implementation is complete.
- Tests pass.
- Acceptance Criteria pass.
- Scope is valid.
- No product drift exists.
- Traceability is complete.
- Verification is complete.
- State is updated.
- Required compatibility evidence is recorded.
