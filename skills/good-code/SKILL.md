---
name: good-code
description: "Use for any software engineering task involving code, including writing, modifying, debugging, refactoring, reviewing, or explaining it. Apply minimalist design principles to produce the smallest clear, correct, secure, maintainable solution; preserve existing behavior; avoid unnecessary abstractions, dependencies, and configuration; and verify the result."
---

# Good Code

Produce the smallest clear, correct, and maintainable solution that fully addresses the current problem.

Prefer minimal software: fewer concepts, dependencies, abstractions, mutable states, public interfaces, configuration options, and moving parts. Minimalism is not code golf or the smallest possible diff. It means removing unnecessary complexity while preserving correctness, clarity, and stability.

Prioritize applicable correctness, security, compatibility, performance,
accessibility, and resource constraints. Within those constraints, prefer
clarity, maintainability, and the smallest stable change. Treat modularity,
decoupling, and testability as proportional means to make the current solution
clearer, safer to change, or simpler to verify—not as ends in themselves.

Follow these principles:

* **KISS:** Prefer the simplest solution that correctly solves the current
  problem. Avoid unnecessary indirection, layers, patterns, and cleverness.

* **YAGNI:** Do not add functionality, abstractions, configuration, or extension
  points for hypothetical future requirements. Implement only what the current
  problem requires.

* **Smallest stable change:** Make the narrowest change that reliably solves the
  problem, not necessarily the smallest textual diff. Address the root cause
  when it is identifiable, within scope, and safe to change; otherwise contain
  the problem at the narrowest reliable boundary.

* **Preserve behavior:** Preserve unrelated observable behavior, interfaces,
  data formats, error semantics, and side effects.

* **Fit the codebase:** Follow the language, platform, constraints, conventions,
  architecture, and suitable existing patterns. Do not reproduce a pattern that
  is clearly incorrect, unsafe, or incompatible with the current requirement.

* **English by default:** Write code and comments in English — identifiers,
  function and type names, file names, and code documentation. Use another
  language only when the user or the repository's standards explicitly require
  it (e.g., locale-specific user-facing strings).

* **Language and ecosystem best practices:** Follow the idiomatic best practices
  of the language in use, its ecosystem, and the project type (e.g., library,
  CLI, web app, embedded). Prefer canonical, widely accepted patterns over
  foreign ones, and rely on the ecosystem's standard solutions unless they
  conflict with the principles above.

* **Reuse suitable mechanisms:** Prefer appropriate existing code, platform
  capabilities, standard libraries, and installed dependencies. Do not force
  reuse when it obscures behavior or increases coupling.

* **Proportional abstraction:** Add or modify abstractions only when they make
  the current solution clearer, safer, or simpler.

* **Explicitness:** Prefer code that is straightforward to understand and
  maintain over code that is clever or theoretically ideal. Avoid hidden
  behavior and implicit coupling.

* **Cohesion and local reasoning:** Keep related behavior together, give each
  unit a clear purpose, and minimize the context required to understand it.

* **Proportional structure:** Modularize, decouple, or introduce test seams
  only when doing so reduces the context needed to understand or safely change
  a unit, or enables narrower relevant verification. Do not add interfaces,
  seams, or layers without those benefits.

* **Minimal surface:** Minimize public APIs, mutable state, configuration,
  dependencies, layers, and extension points.

* **Names over comments:** Express intent through names and structure. Comment
  non-obvious reasons, constraints, invariants, and trade-offs—not mechanics.

* **Necessary refactoring:** Refactor only when required to make the current
  solution correct, clear, or stable. Keep refactoring focused and
  behavior-preserving.

* **Visible assumptions:** When requirements, constraints, or runtime behavior
  are uncertain, state the relevant assumptions instead of silently inventing
  them.

* **Prioritize findings:** In code review, distinguish correctness, security,
  compatibility, and reliability issues from optional maintainability or style
  improvements.

* **Verify the result:** Use the narrowest relevant tests, checks, or
  reproductions. State clearly what was and was not verified.
