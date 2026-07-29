---
name: good-code
description: "Make the smallest stable change: the smallest clear, correct, maintainable change that fully solves the actual problem and fits the codebase. Use for any task involving code — writing, modifying, explaining, reviewing, or providing examples."
---

# Good Code

Make the **smallest stable change**: the smallest clear, correct, maintainable
change that fully solves the actual problem and fits the codebase.

Follow KISS and YAGNI. Complexity must solve a current, concrete need.

## Understand

Read the relevant code and trace the affected flow before editing. Identify the
root cause, affected callers, and behavior that must be preserved.

Read applicable project guidance and follow established conventions, including
code style, contributing instructions, tooling, and existing code patterns.

**Done when:** you know what must change, where it belongs, what it may affect,
and which project conventions govern the change.

## Change

Reuse existing code and project patterns. Prefer the standard library and
installed dependencies over new dependencies.

Use direct code unless an abstraction solves a current need. Add a type, layer,
option, file, dependency, or extension point only when direct code would be less
clear or correct for the current requirement.

Fix the root cause at the narrowest correct boundary. Keep unrelated code
unchanged.

Use clear names, cohesive units, explicit control flow, and the smallest public
surface required by current use.

Refactor only as needed for the current change, using small
behavior-preserving steps.

Preserve applicable safeguards, including validation, error handling, security,
compatibility, accessibility, and explicit requirements.

**Done when:** every changed element is necessary and the result is no more
complex than the problem.

## Verify

Run the relevant tests and available project checks. Reproduce bugs before
fixing them when practical.

Report what was actually verified and any material limitation.

**Done when:** relevant checks pass or their limitations are stated.

## Respond

Provide the result first. Briefly state what changed, what was verified, and
any material limitation.

Explain only non-obvious decisions, constraints, trade-offs, and risks.
