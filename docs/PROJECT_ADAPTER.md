# Universal Project Adapter Standard

## Purpose
The Project Adapter is the bridge between the technology-neutral Universal Development Foundation and the implementation environment actually present in a repository.

`UNIVERSAL FOUNDATION -> PROJECT ADAPTER -> ACTUAL PROJECT TOOLCHAIN`

The adapter describes implementation facts. It does not define application architecture and it does not replace native project configuration.

## Authority
Native project files remain authoritative for implementation-specific configuration. Examples include `Cargo.toml`, `package.json`, `pyproject.toml`, `go.mod`, `pom.xml`, `build.gradle`, `CMakeLists.txt`, and `Makefile`.

The adapter references such files where relevant; it does not copy their full configuration.

## Detected, declared, verified, unknown
These states are distinct:
- `detected`: repository evidence indicates a technology or configuration exists.
- `declared`: the project explicitly claims a technology or command.
- `verified`: executable validation confirmed the claim and evidence is recorded.
- `unknown`: the fact could not be established.
- `unavailable`: the component is known but unavailable in the current execution context.
- `unsupported`: the project explicitly does not support the component.

Detected is not declared. Declared is not verified. A configuration file alone does not make a tool verified.

## Model
The canonical schema is `.foundation/schemas/project-adapter.schema.json`.
The current repository adapter is `.foundation/adapter.json`.

The adapter supports independent collections for languages, runtimes, package managers, compilers, build systems, formatters, linters, test runners, CI systems, packaging systems, deployment systems, documentation systems, and security tools.

Each technology entity carries scope, status, version semantics, detection/declaration/verification basis, native-configuration references, and evidence references.

## Workspaces and polyglot repositories
A repository may be single-project, monorepo, polyglot, multi-application, library, service, infrastructure, mixed, or unknown.

Multiple languages, runtimes, package managers, build systems, and test systems are supported independently. No primary language is required unless the repository actually declares one.

## Commands
The adapter provides standard command categories: `format`, `check`, `test`, `build`, `lint`, `package`, and `release`.

Commands are declarative project facts. They are not scripts owned by the foundation. Unknown commands remain explicitly `unknown`. Verified commands must have evidence references and must be evidence-producing.

## CI and deployment
The adapter can describe CI and deployment when discovered or declared, but this standard does not create CI or modify deployment configuration.

## Current repository
`bjo163/boilerplate` currently contains the foundation, README, and documentation only. Git/GitHub repository metadata is observed, but application language, runtime, package manager, compiler, build system, formatter, linter, test runner, CI, packaging, deployment, environments, and project commands remain unknown.

## Examples
Example adapters live under `.foundation/examples/project-adapters/`. They are documentation examples and do not describe the current repository.
