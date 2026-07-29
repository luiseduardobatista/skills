---
name: to-spec
description: Turn the current conversation and codebase context into an implementation-ready specification that can be implemented directly or decomposed into tickets.
disable-model-invocation: true
---

# To Spec

Create a specification from the decisions and requirements established in the current conversation, referenced sources, and relevant codebase context.

The specification may be a PRD, design-conformance document, or internal engineering specification, depending on the work.

Do not restart discovery or interview the user by default. Ask only when an unresolved ambiguity would materially change scope, behaviour, architecture, compatibility, migration, or verification.

## 1. Gather context

Use all relevant conversation context. If the user supplies a design, issue, ADR, document, prototype, or repository path, read it before drafting.

Inspect the codebase as needed to understand existing behaviour, domain terminology, integration points, architecture, public contracts, test seams, and repository conventions. Respect relevant ADRs, domain documentation, and accepted decisions.

Do not invent requirements, system behaviour, design details, or constraints unsupported by the conversation, sources, or codebase.

## 2. Classify the work and choose a structure

Silently classify the work, then choose the lightest structure that fully describes it. Do not concatenate every possible section into one document.

### Product feature

Use the applicable sections from:

- Problem Statement
- Solution
- User Stories
- Implementation Decisions
- Acceptance Criteria
- Testing Decisions
- Out of Scope, when useful

Use concise user stories for distinct user-facing outcomes, workflows, permissions, failure modes, or meaningful edge cases. Do not split a workflow into stories for every field, visual detail, responsive rule, accessibility requirement, or technical constraint.

### Design conformance or remediation

Use the applicable sections from:

- Problem
- Design References
- Current Discrepancies
- User Flows
- Required Behaviour
- Implementation Constraints
- Acceptance Criteria
- Verification
- Out of Scope, when useful

Use this when implementation diverges from an approved design, specification, reference implementation, or established expected behaviour. Do not force it into user stories: use flows only for distinct end-to-end journeys, and express visual, responsive, accessibility, and interaction details as requirements or acceptance criteria.

### Internal engineering change

Use the applicable sections from:

- Problem
- Current State
- Required Outcome
- Constraints
- Acceptance Criteria
- Verification
- Out of Scope, when useful

Use this for refactors, migrations, performance or infrastructure work, internal correctness fixes, and changes whose actor is a developer, operator, consuming system, or runtime. Describe system behaviour, invariants, compatibility requirements, constraints, and observable outcomes; do not invent an end-user perspective.

### Mixed work

Combine only the sections required for the user-facing outcome and engineering change.

## 3. Keep sections purposeful

Use each section for one purpose:

- User stories or flows: who does what and why.
- Current discrepancies: the gap between existing and expected behaviour.
- Required behaviour: what the system must do.
- Implementation decisions or constraints: accepted technical boundaries and choices.
- Acceptance criteria: observable conditions proving completion.
- Testing decisions or verification: how completion is demonstrated.

Avoid needless duplication. Repeat or reference a requirement where needed to make the specification or acceptance criteria unambiguous.

## 4. Record implementation decisions

Record only applicable decisions that materially constrain implementation, including architecture, ownership boundaries, interfaces and contracts, schemas and payloads, compatibility, state management, responsive behaviour, accessibility, rollout or migration, and relevant repository conventions.

Do not create a file-by-file implementation plan. Avoid volatile file paths and code snippets unless they express an accepted contract or design decision more precisely than prose.

For design-conformance work, distinguish reference measurements from rigid production dimensions; preserve responsive behaviour and repository conventions. When specifying colours, spacing, radii, or shadows, state whether they map to existing or new design tokens.

## 5. Define verification and acceptance

Identify the highest stable seam through which the behaviour can be verified. Prefer existing public seams over internal implementation details, such as a rendered route, public API, CLI, integration boundary, domain-service interface, or operational signal.

Verify observable behaviour rather than private methods, internal state shapes, CSS classes, or incidental implementation structure. Ask the user to confirm a test seam only when that choice materially changes architecture, scope, cost, or confidence.

When automated test infrastructure does not exist, specify proportionate manual, visual, operational, or build-based verification rather than introducing unrelated infrastructure by default.

Acceptance criteria must be observable and testable, not a low-level implementation checklist. Include applicable criteria for:

- **Design conformance:** design structure, content hierarchy, responsive variants, interactions, accessibility, preserved context, and missing capabilities.
- **Internal work:** preserved behaviour, compatibility, correctness, performance thresholds, migration completion, obsolete-path removal, and operational readiness.

## 6. Scope and review

State out-of-scope work when adjacent work could reasonably be mistaken as part of the change. Include positive scope boundaries only when they materially improve clarity; do not add ceremonial empty sections.

Before finalizing, verify that:

- the problem and outcome are clear;
- no unsupported fact or requirement was invented;
- the structure fits the work;
- visual or internal details were not forced into user stories;
- requirements are clear without needless duplication;
- relevant ADRs, designs, contracts, and repository conventions are respected;
- acceptance criteria are observable;
- the verification seam is appropriate;
- the document is proportional and has no unresolved placeholders.

## 7. Publish

Publish through the repository's configured tracker or local documentation convention.

For a tracker, apply its configured implementation-ready status or label, such as `ready-for-implementation`, when one exists. Do not invent a label or require one for local documentation. When no publication convention exists, ask where the user wants the specification stored or published.

Do not create implementation tickets as part of this skill.

After publishing, report where the specification was saved or published, any blocking question or assumption requiring confirmation, and whether the next step is direct implementation or ticket decomposition.
