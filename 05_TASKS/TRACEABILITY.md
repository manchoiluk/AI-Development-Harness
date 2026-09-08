# Traceability

Traceability is the spine of V0.2. Every implemented artifact MUST be traceable from a Requirement down to Verification, and back.

## Forward Chain

```text
Requirement
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
```

## Reverse Chain

```text
Verification
    ↓
Test
    ↓
Implementation
    ↓
Task
    ↓
Design
    ↓
Spec
    ↓
Requirement
```

## Traceability ID

A single, stable ID scheme is used. IDs must be:

- Unique
- Stable
- Human-readable
- Cross-referenceable

Example IDs:

```text
REQ-001     Requirement
SPEC-001    Spec
DESIGN-001  Design
TASK-001    Task
TEST-001    Test
VER-001     Verification
```

Do not design a complex ID system. V0.2 only needs the properties above.

## Traceability Matrix (Template)

| Requirement | Spec | Design | Task | Test | Verification | Status |
|-------------|------|--------|------|------|--------------|--------|
| REQ-001     | SPEC-001 | DESIGN-001 | TASK-001 | TEST-001 | VER-001 | VERIFIED |

> This is only a template example. Do not fill in specific product content.

## Completeness Rules

### Requirement → Spec

Every implemented requirement MUST have a corresponding Spec.

### Spec → Design

A Spec that needs technical design MUST be able to find its Design.

### Design → Task

A Design that needs implementation MUST be decomposable into Tasks.

### Task → Test

A Task MUST have a corresponding test strategy.

### Test → Verification

Test results MUST be able to enter Verification.

### Verification → Requirement

Final Verification MUST be traceable back to the Requirement.

## No Orphan Objects

The following objects MUST NOT exist without a source:

```text
Task
Test
Verification
```

Example: `TASK-999` cannot find its `REQ` and `SPEC`, therefore:

```text
INVALID
```
