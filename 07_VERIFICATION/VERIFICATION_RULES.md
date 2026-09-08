# Verification Rules

A task is verified only when:

1. Required implementation exists.
2. Required tests exist where applicable.
3. Tests pass.
4. Acceptance criteria pass.
5. Scope has not expanded.
6. Product behavior matches approved Spec.
7. Relevant state is updated.

## Verification Record

### Task ID

### Requirement

### Evidence

### Test Result

### Acceptance Result

### Scope Check

### Product Drift Check

### Final Result

PASS / FAIL / BLOCKED

## Requirement Verification

Confirm the implemented behavior matches the approved Requirement.

- Requirement exists and is approved.
- Behavior matches the Requirement, not a reinterpretation.

## Scope Verification

Verify:

- Task Scope
- Files Changed
- Features Changed

against the current Task.

If `Task = A` but the change touched `A + B + C`:

```text
REPORT: Scope Violation
```

## Traceability Verification

Confirm the chain is intact:

```text
Requirement → Spec → Design → Task → Test → Verification
```

Every Task, Test, and Verification MUST have a valid source. Orphan objects are INVALID.

## Product Drift Verification

Check whether the implementation has gradually become a different product.

Check:

- New features added
- Features removed
- Behavior changed
- UX changed
- Scope expanded
- Original requirement replaced

Any one of these without approval:

```text
FAIL
```

## State Verification

Confirm `08_STATE/` matches reality:

- Project State
- Implementation State
- Known Issues

are current and consistent with the work just done.
