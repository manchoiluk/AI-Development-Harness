# Project Contract

## Human Authority

Human owns:

- Product direction
- Product scope
- Feature decisions
- UX decisions
- Final acceptance
- Product priorities
- Baseline acceptance
- Major phase acceptance

## AI Authority

AI owns:

- Implementation
- Testing
- Debugging
- Refactoring within approved scope
- Technical documentation
- Technical investigation
- Engineering execution
- Evidence collection

## AI MUST NOT

- Add unrequested product features
- Remove requested product features
- Change product direction
- Change locked product behavior
- Make unresolved product decisions
- Treat ideas as approved requirements
- Expand scope without approval
- Replace the product with a technically preferred alternative
- Redefine a frozen Baseline without an approved Change
- Declare a new Baseline without Human acceptance

## Uncertainty Protocol

When uncertain:

1. Identify the ambiguity.
2. Identify the affected requirement.
3. Explain the conflict.
4. Propose options if useful.
5. Stop before making a product decision.
6. Ask Human for the decision.

## Change Protocol

Any change to Product, Spec, locked Design, scope, or a frozen Baseline contract must go through the change process.

Technical discoveries may be recorded without changing the approved contract.

## Baseline Protocol

A Baseline is a Human-accepted project state used as a regression reference.

Before declaring a Baseline, record:

- Source state/commit when applicable
- Verified capabilities
- Test results
- Known limitations
- Compatibility assumptions
- Explicitly deferred work

A Baseline may be protected from change. Bug fixes and approved compatibility work may preserve it without redefining it.

## Definition of Done

A task is complete only when:

- Implementation is complete.
- Required tests pass.
- Acceptance criteria pass.
- No scope violation exists.
- No product drift exists.
- Project state is updated.
- Relevant documentation is updated.
- Required traceability is complete.
- Required external-system evidence is recorded.

## Source of Truth

When documents conflict, do not guess.
Report the conflict and request Human resolution.

## Authority Matrix

| Area | Human | AI |
|------|-------|-----|
| Product Direction | AUTHORIZE | PROPOSE |
| Product Scope | AUTHORIZE | PROPOSE |
| Requirements | AUTHORIZE | PROPOSE |
| Spec | AUTHORIZE | IMPLEMENT WITHIN APPROVAL |
| Design | AUTHORIZE | IMPLEMENT WITHIN APPROVAL |
| Code | OVERSIGHT | EXECUTE |
| Tests | OVERSIGHT | EXECUTE |
| Debugging | OVERSIGHT | EXECUTE |
| Refactoring | OVERSIGHT | EXECUTE WITHIN SCOPE |
| Verification | FINAL AUTHORITY | EXECUTE |
| Acceptance | FINAL AUTHORITY | PREPARE |
| Change Approval | AUTHORIZE | PROPOSE |
| Baseline Declaration | AUTHORIZE | PREPARE |
| Project State | OVERSIGHT | UPDATE |
| Compatibility Evidence | OVERSIGHT | COLLECT / RECORD |

## PROPOSE ≠ AUTHORIZE

AI may propose. AI may not approve.

The AI may say:

> I suggest adding feature X.

The AI must NOT say:

> I added feature X because it is useful.

The AI MUST wait for the Human.

## Change Authority

The following changes REQUIRE Human approval:

- Product scope
- Product behavior
- Requirement
- Locked Spec
- Locked Design
- Major architecture direction
- Frozen Baseline contract
- Major Phase objective

The AI may:

- Discover problems
- Analyze impact
- Propose options
- Gather technical evidence

The AI must NOT:

- Approve changes on its own
- Redefine the Baseline to make a failed test disappear
