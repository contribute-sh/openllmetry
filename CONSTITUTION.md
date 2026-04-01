# Constitution

Version: 1.0.0  
Date: 2026-04-01

## Purpose

This fork of `openllmetry` exists to provide a lean, MIT-licensed JavaScript foundation for open-source observability in LLM applications. It should remain easy to audit, easy to extend, and safe for automated coding agents to improve in small, reviewable increments. Backward compatibility is the default requirement: existing users, integrations, and emitted telemetry must keep working unless this constitution is formally amended.

## Principles

- Correctness first: emitted telemetry must reflect real application behavior, not approximations or convenient guesses.
- Test coverage is mandatory: every new behavior, bug fix, or regression fix must add automated coverage or a deterministic verification artifact until a formal test runner is in place.
- Backward compatibility is the default: preserve public APIs, configuration, and telemetry semantics across routine changes.
- Observability must be useful for LLM applications: prioritize clear spans, actionable metadata, and debugging value over feature count.
- Open-source clarity over cleverness: prefer readable JavaScript, explicit control flow, and behavior that contributors can easily audit.
- Minimal core by default: keep the runtime small, dependency-free, and straightforward to embed in other systems.

## Boundaries

- Will NOT add new runtime dependencies.
- Will NOT change the public API without an amendment.
- Will NOT remove or weaken existing tests.
- Will NOT introduce vendor-specific lock-in into the core package or telemetry format.
- Will NOT capture secrets, API keys, or raw prompt/response content by default.
- Will NOT add instrumentation that materially changes application behavior outside its observability scope.
- Will NOT rename or repurpose established span names, attributes, or configuration keys without an amendment and migration plan.

## Quality Standards

- JSDoc on all exported functions.
- No function longer than 50 lines.
- Diff size under 500 lines per task.
- Every behavior change must include automated verification; until a test runner exists, this means a checked-in deterministic `node` script or fixture with documented execution steps.
- Every public API, configuration, or telemetry-schema change must update documentation in the same diff.
- All new code must use plain JavaScript supported by the project's documented runtime target and avoid dead code, unused exports, and commented-out logic.

## Roadmap

1. Establish the JavaScript package scaffold, module boundaries, and contributor workflow for this fork.
2. Add a test runner and CI pipeline with smoke, regression, and integration coverage for core instrumentation paths.
3. Define and document the stable public API, configuration surface, and semantic versioning policy.
4. Implement OpenTelemetry-compatible tracing for priority JavaScript LLM SDKs and framework entry points.
5. Add privacy controls, including redaction hooks, safe defaults, and explicit opt-in for sensitive payload capture.
6. Add performance benchmarks, sampling controls, and overhead budgets for hot-path instrumentation.
7. Publish clear documentation and examples for setup, local verification, and migration from upstream behavior.
