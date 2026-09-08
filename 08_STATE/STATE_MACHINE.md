# State Machine

Defines the allowed lifecycle of a Task. The AI MUST NOT move a Task through illegal transitions.

## Normal Flow

```text
BACKLOG
   ↓
READY
   ↓
IN_PROGRESS
   ↓
IMPLEMENTED
   ↓
TESTING
   ↓
VERIFIED
   ↓
COMPLETED
```

## Exception State

```text
BLOCKED
```

Allowed entries:

```text
IN_PROGRESS → BLOCKED
TESTING → BLOCKED
VERIFIED → BLOCKED
```

After unblocked:

```text
BLOCKED → IN_PROGRESS
```

## Forbidden Transitions

The following jumps are NOT allowed. Each stage MUST be passed through:

```text
BACKLOG → COMPLETED
BACKLOG → VERIFIED
READY → COMPLETED
IN_PROGRESS → COMPLETED
IMPLEMENTED → COMPLETED
```

## State Definitions

Each state defines: Meaning, Entry Conditions, Exit Conditions, Allowed Actions, Forbidden Actions.

### BACKLOG

- Meaning: Task exists but is not ready.
- Entry: Created from a Requirement/Spec/Design.
- Exit: Requirements, Spec, Design, Acceptance Criteria, and Source are all defined.
- Allowed: Refine, link sources, move to READY.
- Forbidden: Implementation by AI.

### READY

- Meaning: Task is fully defined and traceable.
- Entry: All sources and Acceptance Criteria present.
- Exit: Work starts.
- Allowed: Move to IN_PROGRESS.
- Forbidden: Mark complete, skip stages.

### IN_PROGRESS

- Meaning: Implementation ongoing.
- Entry: From READY.
- Exit: Implementation done and self-checked.
- Allowed: Implement, DEBUG, move to IMPLEMENTED or BLOCKED.
- Forbidden: Mark COMPLETED/TESTING without implementation.

### IMPLEMENTED

- Meaning: Code written, not yet tested.
- Entry: Implementation complete.
- Exit: Tests started.
- Allowed: Move to TESTING.
- Forbidden: Mark VERIFIED/COMPLETED.

### TESTING

- Meaning: Tests running.
- Entry: From IMPLEMENTED.
- Exit: Tests pass.
- Allowed: Run tests, DEBUG, move to VERIFIED or BLOCKED.
- Forbidden: Mark COMPLETED on test failure.

### VERIFIED

- Meaning: Tests pass and Verification passed.
- Entry: Verification passed.
- Exit: State updated.
- Allowed: Move to COMPLETED, or BLOCKED if a late issue appears.
- Forbidden: Mark COMPLETED without state update.

### COMPLETED

- Meaning: Fully done and closed.
- Entry: All Completion Gate conditions met.
- Exit: None (terminal for this Task).
- Allowed: Archive to completed/.
- Forbidden: Reopen without a new Task/Change.

### BLOCKED

- Meaning: Cannot legally continue right now.
- Entry triggers:
  - Missing Requirement
  - Conflicting Spec
  - Missing Decision
  - Technical Blocker
  - Failed Verification
  - Human Decision Required
- Exit: The blocking condition is resolved.
- Allowed: Move to IN_PROGRESS after resolution; report blocker.
- Forbidden: Treat BLOCKED as failure; silently skip the Task.

> BLOCKED is not failure. It means the Task cannot legally continue yet.
