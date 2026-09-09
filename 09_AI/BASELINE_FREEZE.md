# Baseline Freeze

A completed milestone may be declared a **Baseline**. Once frozen, the baseline becomes the compatibility and regression reference for subsequent work.

## Purpose

Baseline Freeze prevents AI development from continuously changing a working foundation while new features are being built.

A baseline is not abandoned. It is protected.

## Baseline Record

Every frozen baseline MUST record:

- Baseline ID
- Date
- Product/Project version if applicable
- Source commit/tag if applicable
- Verified requirements
- Verified capabilities
- Test commands and results
- Known limitations
- Known compatibility assumptions
- Explicitly deferred work

Recommended location:

```text
08_STATE/BASELINE_<ID>.md
```

## Freeze Rules

After a baseline is frozen, AI MAY:

- Fix regressions against the baseline
- Fix security or correctness defects
- Fix tests and verification infrastructure
- Fix documentation errors
- Add compatibility evidence

AI MUST NOT silently:

- Change approved behavior
- Remove or rename public behavior
- Add unrelated features
- Redefine domain semantics
- Change a locked architecture decision
- Treat a future feature as part of the baseline

Any change that affects the baseline contract MUST go through the Change Protocol and receive Human approval.

## Baseline vs Next Phase

```text
Frozen Baseline
      ↓
Protected Contract
      ↓
Next Phase
      ↓
New Tasks
      ↓
New Verification
```

New work must not modify the baseline definition merely because implementation has started.

## Exit From Freeze

A baseline can only be superseded by a new approved baseline after:

1. New requirements/specifications are approved.
2. The next phase is completed.
3. Regression tests against the previous baseline pass or documented exceptions are approved.
4. Verification is complete.
5. Human accepts the new baseline.
