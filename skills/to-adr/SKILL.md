---
name: to-adr
description: Record a settled decision as an Architecture Decision Record (ADR). Use when a decision is made that a future reader would otherwise question.
disable-model-invocation: true
---

Turn a decision made in this conversation into an ADR, saved to `docs/adr/`.

## When to record

Offer (or record, if asked directly) an ADR only when **all three** hold:

1. **Hard to reverse** — the cost of changing your mind later is meaningful
2. **Surprising without context** — a future reader will look at the code and wonder why it is this way
3. **The result of a real trade-off** — there were genuine alternatives and one was picked for specific reasons

If any is missing, skip it: an easy-to-reverse decision will just be reversed; an unsurprising one raises no questions; an obvious choice has nothing to say.

What qualifies:

- **Architectural shape** — monorepo vs multi-repo, event-sourced write model, etc.
- **Integration patterns between contexts** — events, synchronous calls, shared databases
- **Technology choices with lock-in** — database, message bus, auth provider, deployment target. Not every library — only the ones that would take a quarter to swap out
- **Boundary and scope decisions** — who owns what; the explicit no-s matter as much as the yes-s
- **Deliberate deviations from the obvious path** — anything where a reasonable reader would assume the opposite
- **Constraints invisible in the code** — compliance, performance contracts, partner API deadlines
- **Rejected alternatives when the rejection is non-obvious** — otherwise someone will re-suggest the same option in six months

## Format

```md
# {Short title of the decision}

{1-3 sentences: the context, what was decided, and why.}
```

That is it. An ADR can be a single paragraph. Its value is recording *that* a decision was made and *why* — not in filling out sections.

Optional sections, only when they add genuine value:

- **Status** frontmatter (`proposed | accepted | deprecated | superseded by ADR-NNNN`)
- **Considered Options** — when the rejected alternatives are worth remembering
- **Consequences** — when non-obvious downstream effects need calling out

## Mechanics

- **Follow the project's own convention.** Record decisions where the project already records them — `docs/adr/`, `docs/decisions/`, ADRs at the repo root — with the same numbering style. If the project has its own ADR format, use it instead of the template above.
- **Numbering**: files are sequentially numbered (`0001-slug.md`, `0002-slug.md`...). Scan for the highest existing number and increment by one.
- **Don't create infrastructure unasked.** If the project has no ADR location, offer to create `docs/adr/` in one line and wait — it's the user's call.
- Write the file yourself and confirm with the user.