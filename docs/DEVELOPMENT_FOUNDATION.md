# Development Foundation

## Purpose
This repository uses a project-independent development control layer around implementation. It does not force a language, framework, package manager, build system, CI provider, hosting provider, or deployment model.

## Required lifecycle
`DISCOVER -> AUDIT -> MODEL -> PLAN -> APPROVE -> EXECUTE -> VERIFY -> REPORT -> STATE UPDATE`

Success must never be reported before verification.

## Logical roles
| Role | Path |
| --- | --- |
| Manifest | `.foundation/manifest.json` |
| Schemas | `.foundation/schemas/` |
| Contracts | `.foundation/contracts/` |
| Tasks | `.foundation/tasks/` |
| Executions | `.foundation/executions/` |
| Evidence | `.foundation/evidence/` |
| Artifacts | `.foundation/artifacts/` |
| Reports | `.foundation/reports/` |
| Decisions | `.foundation/decisions/` |
| Project adapter | `.foundation/adapter.json` |
| Agent policy | `.foundation/policies/agent-policy.json` |

## Current adapter
At bootstrap the repository was greenfield and empty. Git/GitHub and the `main` default branch are observed. Language, runtime, package manager, build system, formatter, linter, test runner, CI, packaging, and deployment remain `unknown` or `unconfigured` until implementation establishes them.

## Identity, time, and versioning
When no existing task identity exists, ordered records default to 13-digit monotonic numeric IDs. Timestamps use RFC 3339 / ISO 8601-compatible form. Schema, document, contract, task, artifact, and implementation versions advance independently.

## Model separation
A schema describes structure. A contract describes rules. A task describes intended work. An execution records an attempt. Evidence supports observations. Verification evaluates requirements. A report records what actually happened. These concepts must not collapse into one success boolean.

## Safety
Read is preferred. Create and modify are scoped. Delete, secrets, and administrative operations are denied unless explicitly authorized. Destructive operations require an explicit decision.

## Decisions
Do not create decision records merely to populate a directory. Add one only when an important architecture or governance choice has actually been made.

## Verification
Actual build/test/lint commands come from `.foundation/adapter.json`. Until project tooling exists, verification is limited to foundation JSON/schema/reference checks and GitHub repository read-back. Never invent application commands.
