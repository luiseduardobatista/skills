---
name: to-tickets
description: Break an implementation-ready specification, plan, or conversation into small, independently understandable tracer-bullet tickets with explicit dependencies.
disable-model-invocation: true
---

# To Tickets

Turn an implementation-ready specification, plan, or current conversation into implementation tickets.

Each ticket must be understandable and executable by a developer who has not read the full parent specification. The parent specification remains the source of truth for broader context, but essential requirements must not be hidden behind a link.

## 1. Gather context

Work from the current conversation and any referenced specification, plan, issue, ADR, design, or repository path.

If the user provides a reference, read the complete relevant artifact before drafting tickets.

Inspect the codebase when needed to understand:

- current behaviour;
- domain terminology;
- integration points;
- ownership boundaries;
- public contracts;
- test seams;
- repository and tracker conventions.

Respect relevant ADRs and accepted decisions.

If unresolved questions materially affect scope, architecture, contracts, migration order, or acceptance, surface them before decomposition.

## 2. Draft tracer-bullet tickets

Prefer narrow, complete vertical slices.

Each ticket should make one meaningful behaviour, capability, or outcome demonstrably true.

A ticket should:

- cross every layer required for that outcome;
- be independently verifiable;
- fit within one focused implementation session;
- leave the repository in a coherent state;
- preserve applicable constraints and invariants.

Do not split work only by technical layer, such as schema, backend, frontend, styling, and tests, when a vertical slice is possible.

For broad refactors or migrations that cannot safely land as vertical slices, use expand-contract:

1. Expand: introduce the new form beside the old.
2. Migrate: move consumers in safe, verifiable batches.
3. Validate: prove compatibility, correctness, performance, or operational readiness.
4. Contract: remove the old form when the required conditions are satisfied.

Create explicit cleanup or removal tickets when legacy code, flags, adapters, or compatibility paths must be deleted.

## 3. Make every ticket self-contained

Each ticket must be independently understandable and executable by a developer who has not read the full source specification.

Copy or restate all requirements, constraints, and acceptance criteria that materially apply to that ticket.

Do not require the implementer to navigate to the parent specification to discover essential requirements.

Reference the parent specification for broader context, rationale, and decisions outside the ticket's scope.

Do not copy unrelated sections or reproduce the entire specification.

When a requirement applies to multiple tickets, repeat it in each affected ticket when omitting it could cause an incorrect implementation.

Prefer deliberate duplication over hidden dependencies on the reader's memory or prior knowledge.

## 4. Declare genuine dependencies

Give every ticket explicit blocking edges.

Declare only genuine blockers, such as:

- a required contract does not exist yet;
- a prerequisite behaviour is unavailable;
- a migration gate has not been satisfied;
- validation depends on an earlier slice;
- removal depends on all consumers being migrated.

Do not block a ticket merely because another ticket appears earlier in the list.

A ticket with no blockers can start immediately.

## 5. Review the breakdown

Before publishing, present a concise preview containing:

- title;
- outcome;
- blockers;
- any important scope boundary.

Ask whether:

- the granularity is appropriate;
- the dependency edges are correct;
- any ticket should be merged, split, removed, or reordered.

Iterate until approved unless the user explicitly requests immediate publication.

## 6. Publish

Use the repository's configured tracker or local ticket convention.

In local mode, write one file per ticket under the configured location. When no convention exists, prefer:

`.scratch/<feature-slug>/issues/<NN>-<slug>.md`

In tracker mode, create one issue per ticket in dependency order so blocking relationships can reference real identifiers.

Use native dependency relationships for blockers. Use sub-issue relationships only for the intended hierarchy; do not use them as a substitute for a blocking edge.

Apply the repository's configured implementation-ready status or label, such as `ready-for-implementation`, after approval when the ticket is fully specified and can be executed once its declared dependencies are satisfied.

Blocking dependencies do not make a ticket unready. They only determine when the ticket may start.

Do not mark a ticket implementation-ready when it still contains an unresolved design question or missing requirement.

Do not close or modify the parent specification or issue unless explicitly requested.

## Ticket template

```markdown
# <Outcome-oriented title>

Status: ready-for-implementation

## Context

Briefly explain the problem and why this slice exists.

Keep this local to the ticket. Do not reproduce the entire parent specification.

## Outcome

Describe the end-to-end behaviour or system capability that becomes true when this ticket is complete.

Use the perspective of the relevant actor: user, operator, developer, consuming system, or runtime.

Do not provide a layer-by-layer implementation checklist.

## Requirements

Include every requirement and constraint from the parent specification that materially applies to this ticket.

- Required behaviour
- Relevant implementation constraint
- Applicable responsive, accessibility, compatibility, migration, or operational rule

Do not include unrelated requirements.

## Acceptance criteria

- [ ] Observable and testable criterion
- [ ] Observable and testable criterion

## Verification

Briefly explain how completion will be demonstrated or tested.

Omit this section when the acceptance criteria already make verification obvious.

## Out of scope

Include this section only when adjacent work could reasonably be mistaken as part of the ticket.

Keep it short and specific. Do not copy the parent specification's full out-of-scope list.

## Blocked by

- <ticket reference and genuine blocking reason>

Or:

None — can start immediately.

## Parent specification

<Link, issue, or repository path>

## Notes

Include only decision-relevant context that cannot be inferred from the requirements above.

Avoid volatile file paths, file-by-file implementation instructions, and code snippets unless they express an accepted contract more precisely than prose.
```

## 7. Final checks

Before publishing, verify that:

- every ticket delivers a coherent outcome;
- every ticket contains the requirements needed to implement it correctly;
- no ticket depends on reading the full parent specification for essential information;
- acceptance criteria are observable;
- blockers are genuine;
- adjacent scope is excluded where necessary;
- the set of tickets covers all material work in the source specification;
- cleanup and removal work is explicit when required.
