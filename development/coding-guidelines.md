---
name: coding-guidelines
description: Coding guidelines for software development.
category: development
arguments: []
tags:
  - guidelines
  - coding-standards
  - best-practices
---
# Software Development & Review Guidelines (Language-Agnostic)

**SCOPE & MINDSET**
- Think like a system architect first, coder second: clarify goals, constraints, and expected behaviors.
- Prefer clean, modern designs over incremental patching.
- **Backward Compatibility & Legacy Code:** Unless explicitly requested, do **not** preserve backward compatibility, shim old behavior, or retain legacy APIs/structures. Remove dead code, deprecated paths, and ad-hoc workarounds in favor of the best current patterns and principles. Clearly note any intentional breaking changes.

**CODE STYLE & FORMATTING**
- Follow the dominant community conventions of the target language/framework.
- Be consistent with whitespace, naming, and file/module organization.
- Use clear, descriptive names that convey purpose and domain meaning.
- Keep functions and methods small and cohesive; prefer readability over cleverness.
- Delete unused code and comments; avoid commented-out blocks.

**ARCHITECTURE & DESIGN PRINCIPLES**
- Encapsulate complexity behind clear module and API boundaries.
- Favor composition over inheritance; depend on abstractions (interfaces/ports), not concretions.
- Strive for single responsibility per unit; isolate side effects; keep pure logic testable and deterministic.
- Apply proven patterns when they simplify reasoning (e.g., dependency injection, strategy, adapter, CQRS, hexagonal/clean architecture).
- Keep configuration out of code; prefer environment or declarative config with defaults.
- Use best design principles, but do not over-engineer. Avoid unnecessary abstractions, layers, or patterns that add complexity without clear benefit.

**ERROR HANDLING & RESILIENCE**
- Fail fast on programmer errors; provide actionable messages for user/runtime errors.
- Use explicit error types/categories; avoid swallowing exceptions.
- Never leak secrets or PII in error messages or logs.

**DOCUMENTATION**
- Write clear, concise documentation for modules, classes, and functions
- Use language-appropriate documentation formats (JSDoc, XML docs, docstrings, etc.)

**COMMENTS**
- Comment *why*, not *what*. Capture intent, business rules, and tricky algorithms.
- Avoid restating obvious code or adding meta commentary. Do **not** comment on your own changes.
- Update or remove stale comments.

**TESTING STRATEGY**
- Test behavior and public contracts, not internal implementation details.
- Cover edge cases, error paths, concurrency/race conditions, and representative user workflows.
- Include both unit tests (fast, isolated) and integration/contract tests (real IO, services) when applicable.
- Write tests that verify behavior and business logic, not implementation details (i.e. what the code does (its observable behavior) rather than how it does it (the internal mechanics))
- Skip trivial or 'low value' tests (simple getters/setters, obvious assignments)
- Use fixtures/factories for setup; keep tests deterministic (seed PRNGs, avoid sleeps and non-deterministic ordering).
- Use mocks/stubs only at architectural boundaries; prefer real objects elsewhere.
- Do **not** use print/debug output as assertions; failures must be explicit and informative.
