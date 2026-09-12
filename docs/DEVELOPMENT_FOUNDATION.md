# Development Foundation

## Purpose
This repository uses a project-independent development control layer around implementation. It does not force a language, framework, package manager, build system, CI provider, hosting provider, or deployment model.

## Lifecycle
`DISCOVER -> AUDIT -> MODEL -> PLAN -> APPROVE -> EXECUTE -> VERIFY -> REPORT -> STATE UPDATE`

Success must never be reported before verification.

## Canonical meta-model v2
The canonical schema is `.foundation/schemas/foundation.schema.json` at semantic version **2.0.0**. Historical records remain evidence; new records use explicit v2 semantics.

Identity, actor, source, issuer, executor, owner, capability, permission, policy, operation, evidence, verification, report, decision, reference, version, artifact and state remain distinct concepts.

## Project Adapter Standard
The canonical Project Adapter Standard is version **1.0.0** and is defined by `.foundation/schemas/project-adapter.schema.json`.

The Project Adapter connects the universal foundation to repository-specific technology facts without choosing the technology. It distinguishes `detected`, `declared`, `verified`, `unavailable`, `unsupported`, and `unknown`.

Native project configuration remains authoritative. The adapter references native configuration rather than becoming a second build system, package manager, CI pipeline, or deployment manifest.

The current adapter is `.foundation/adapter.json`. Detailed documentation is in `docs/PROJECT_ADAPTER.md`.

## Polyglot and workspace support
The adapter supports single-project, monorepo, polyglot, multi-application, library, service, infrastructure, mixed, and unknown workspace forms. Multiple languages, runtimes, package managers, build systems, and test systems can coexist independently.

## Verification
A tool or command is `verified` only after executable validation produces evidence. Existing configuration alone is detection evidence, not verification.

## Version and schema evolution
Foundation meta-model, Project Adapter Standard, adapter object, task, contract, artifact, and implementation versions advance independently.

## State and history integrity
State remains multidimensional across object, task, execution, verification, and artifact. Historical task `0000000000001` records remain immutable evidence; the discrepancy found and repaired by task `0000000000002` remains recorded prospectively.

## Logical roles
The authoritative path map is `.foundation/manifest.json`. First-class verification records are in `.foundation/verifications/`, and adapter examples are in `.foundation/examples/project-adapters/`.

## Safety
The Project Adapter describes the implementation environment; it does not define the implementation itself. No application feature, Heartwood migration, technology-stack selection, CI creation, deployment change, framework installation, secret modification, or history rewrite is authorized by this task.
