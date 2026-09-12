# Development Foundation

## Purpose
This repository uses a project-independent development control layer around implementation. It does not force a language, framework, package manager, build system, CI provider, hosting provider, or deployment model.

## Lifecycle
`DISCOVER -> AUDIT -> MODEL -> PLAN -> APPROVE -> EXECUTE -> VERIFY -> REPORT -> STATE UPDATE`

Success must never be reported before verification.

## Canonical meta-model v2
The canonical schema is `.foundation/schemas/foundation.schema.json` at semantic version **2.0.0**. The v2 change is additive/normalizing: historical v1 records are preserved, while new records use explicit canonical semantics.

The foundation distinguishes:
- **Identity**: stable identity of an entity.
- **Actor**: identity acting in an operation.
- **Source**: origin of a document, observation, or artifact.
- **Issuer**: authority that issued or signed something.
- **Executor**: runtime or agent that actually performed an operation.
- **Owner**: identity responsible for an object where applicable.
- **Capability**: available ability.
- **Permission**: authorization for an operation.
- **Policy**: declarative rule deciding an effect.
- **Operation**: action requested or executed.
- **Evidence**: sourced observation supporting a claim.
- **Verification**: comparison of expected and observed conditions, traceable to evidence when applicable.
- **Report**: record of what actually happened.
- **State**: typed state dimension for an object, task, execution, verification, or artifact.

Identity is not authentication. Authentication is not authorization. Authorization is not trust. Actor is not source. Capability is not permission. Evidence is not verification.

## Reference and relationship model
References contain target `type`, `id`, optional `namespace` and `version`, plus a canonical `relationship`.

Canonical relationships:
`depends_on, derived_from, produces, consumes, executes, executed_by, reports_on, verifies, supports, blocks, supersedes, superseded_by, references, contains, generated_from, tracks`

## Version and schema evolution
Schema, document/object, contract, task, artifact, and implementation versions advance independently.

- additive change: non-breaking when previously valid records remain valid;
- deprecation: explicit notice plus compatibility window;
- breaking change: new version, migration rules, decision record, and affected-reference updates;
- migration: preserves provenance and historical evidence;
- supersession: explicit predecessor/successor relationship.

## Verification
Verification is first-class (`project.verification`) and records subject, method, expected condition, observed condition, evidence references, result, timestamp, and verifier.

Results: `passed, failed, inconclusive, not_run, blocked`.

## State
State is multidimensional. `object`, `task`, `execution`, `verification`, and `artifact` states are not collapsed into one boolean.

## History integrity
Historical task `0000000000001` records are immutable evidence. Task `0000000000002` discovered that the existing `.foundation/state.json` was malformed even though the historical bootstrap report had claimed state validation PASS. The historical report was not edited. The current state document was repaired prospectively and the discrepancy is recorded in task `0000000000002` evidence, verification, decision, state, and report.

## Logical roles
The authoritative logical-path map is `.foundation/manifest.json`. Validation examples are in `.foundation/examples/`, and first-class verification objects are in `.foundation/verifications/`.

## Safety
No application source, Heartwood migration, application crate, language selection, deployment, secret, or invented toolchain is part of this foundation hardening.
