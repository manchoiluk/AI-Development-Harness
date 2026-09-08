# Project Contract

## Human Authority

Human owns:

- Product direction
- Product scope
- Feature decisions
- UX decisions
- Final acceptance
- Product priorities

## AI Authority

AI owns:

- Implementation
- Testing
- Debugging
- Refactoring
- Technical documentation
- Technical investigation
- Engineering execution

## AI MUST NOT

- Add unrequested product features
- Remove requested product features
- Change product direction
- Change locked product behavior
- Make unresolved product decisions
- Treat ideas as approved requirements
- Expand scope without approval
- Replace the product with a technically preferred alternative

## Uncertainty Protocol

When uncertain:

1. Identify the ambiguity.
2. Identify the affected requirement.
3. Explain the conflict.
4. Propose options if useful.
5. Stop before making a product decision.
6. Ask Human for the decision.

## Change Protocol

Any change to Product, Spec, locked Design, or scope must go through the change process.

## Definition of Done

A task is complete only when:

- Implementation is complete.
- Required tests pass.
- Acceptance criteria pass.
- No scope violation exists.
- No product drift exists.
- Project state is updated.
- Relevant documentation is updated.

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
| Refactoring | OVERSIGHT | EXECUTE |
| Verification | FINAL AUTHORITY | EXECUTE |
| Acceptance | FINAL AUTHORITY | PREPARE |
| Change Approval | AUTHORIZE | PROPOSE |
| Project State | OVERSIGHT | UPDATE |

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

The AI may:

- Discover problems
- Analyze impact
- Propose options

The AI must NOT:

- Approve changes on its own
