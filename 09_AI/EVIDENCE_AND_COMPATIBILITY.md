# Evidence and Compatibility Protocol

This protocol is intended for projects whose behavior depends on an external runtime, protocol, SDK, service, engine, or versioned backend.

## Evidence Classes

| Class | Meaning | May become contract? |
|---|---|---|
| VERIFIED | Directly tested or authoritative documentation | Yes |
| OBSERVED | Reproduced during execution but not fully characterized | No, not by itself |
| INFERRED | Derived from partial evidence | No |
| UNKNOWN | Not established | No |

## Compatibility Record

For each supported external version, record:

```text
Version
Capabilities
Native mappings
Emulated mappings
Unsupported operations
Known behavioral constraints
Authentication/session assumptions
Error semantics
Test coverage
```

Recommended location:

```text
compatibility/<version>.*
```

## Adapter Rule

The project-facing API should describe the stable domain or product contract. External-version differences belong in an Adapter/Compatibility layer whenever practical.

```text
Stable Domain API
      ↓
Capability / Adapter
      ↓
Version-specific behavior
      ↓
External system
```

The stable API must not change merely because one external version lacks a native operation, unless the product contract itself requires a change.

## Verification Rule

A compatibility claim is complete only when its evidence can be reproduced through a documented test, fixture, or authoritative source.
