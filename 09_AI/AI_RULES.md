# AI Rules

## Rule 1 — Read Before Act

Before changing anything, AI must read:

1. PROJECT_CONTRACT.md
2. Relevant Product documents
3. Relevant Spec documents
4. Relevant Design documents
5. Current Project State
6. Current Task

## Rule 2 — Follow the Hierarchy

Product > Spec > Design > Task > Code

Implementation must not override higher-level intent.

## Rule 3 — No Scope Expansion

AI must not add functionality merely because it appears useful.

## Rule 4 — No Product Decisions

AI may make technical decisions within approved boundaries.

AI may not make unresolved product decisions.

## Rule 5 — Small Changes

Prefer the smallest change that satisfies the Task.

## Rule 6 — Evidence

Do not claim something is complete without evidence.

## Rule 7 — Update State

After meaningful work, update the relevant state documents.

## Rule 8 — Stop on Ambiguity

Do not guess when ambiguity affects product behavior.

## Rule 9 — Preserve Traceability

Every implementation task MUST be traceable to an approved requirement.

## Rule 10 — No Silent Changes

Do not silently modify Product, Spec, or locked Design documents.

## Rule 11 — Do Not Guess

If any of the following occur, the AI MUST STOP and must NOT guess:

- Ambiguous Requirement
- Conflicting Documents
- Missing Specification
- Missing Acceptance Criteria
- Missing Decision

## Rule 12 — Do Not Improve Product

The AI MUST NOT add product behavior because of:

- Better UX
- Better Architecture
- Better Performance
- Better Security
- More Complete Feature

The AI's job is to implement approved intent, not to improve the product on its own.

## Rule 13 — Do Not Repair Requirements

If a requirement appears unreasonable, the AI MUST NOT modify it directly.

The AI MUST:

1. Report the Problem.
2. Explain the Impact.
3. Propose Options.
4. Request Human Decision.

## Rule 14 — No Silent Scope Change

Any change to:

- Product
- Spec
- Design
- Scope

MUST be explicitly recorded.

The AI MUST NOT:

- Secretly modify
- Conveniently modify
- Modify for implementation convenience

## Rule 15 — Evidence Required

The AI MUST NOT use:

- "should be fine"
- "looks okay"
- "theoretically complete"
- "should pass"

in place of verification.

The AI MUST provide:

- Test Result
- Verification Result
- Changed Files
- Evidence
