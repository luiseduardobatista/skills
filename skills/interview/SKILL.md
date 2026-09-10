---
name: interview
description: Sharpen a plan, design, or idea through a relentless, round-by-round interview.
disable-model-invocation: true
---

Interview me relentlessly about every aspect of this until we reach a shared understanding. You are looking for the things I have not decided yet — the branches of the decision tree whose answers I am silently assuming.

## Ask in rounds

- Work in **rounds**: batch a few related questions at once, but only ones whose answers would not change the options or recommendation of another question in the same batch. A question that depends on an answer still open in this round belongs to a later round.
- For every question, give your **recommended answer**.
- If your environment offers a structured way to present several questions at once (each with answer options, all answers collected in a single response), use it for each round; otherwise, ask the round as a short numbered list in one message.
- Wait for all my answers before continuing.

## Probe with scenarios

When domain relationships are being discussed — the boundaries between concepts — stress-test them with a specific scenario: invent one edge case and work it through. It forces precision about where one concept ends and another begins.

## Separate facts from decisions

- **Facts are yours**: if something can be found by exploring the environment (filesystem, tools, documentation, codebase), look it up rather than asking me.
- **Decisions are mine**: put each one to me and wait for my answer.

## Keep going until the tree is exhausted

The interview is done when every branch has been visited and nothing is left silently assumed. Do not act — no implementation, no commits, no writing — until I confirm we have reached a shared understanding.

## Leave a paper trail when there is a project

If this conversation concerns a project on disk — a repository, or a working directory with code or docs — capture what crystallises as you go, inline, following the project's own documentation conventions. Don't invent new ones.

### Glossary

When a term is resolved and the project already keeps a glossary — `CONTEXT.md`, `GLOSSARY.md`, a terminology section in its docs — record the term there, one entry per term, tight:

```md
**Order**:
A request to fulfill a purchase, confirmed once payment clears.
_Avoid_: Purchase, transaction
```

Rules: be opinionated (pick one word, list the rest under `_Avoid_`); keep definitions to one or two sentences saying what the term *is*; only project-specific terms belong — general programming concepts do not.

If the project has no glossary, don't create one — offer it in one line ("I can start a glossary if you want it"). Either way, use the resolved term consistently for the rest of the conversation.

### Decisions

When a decision is hard to reverse, surprising without context, or the result of a real trade-off, offer to record it as an ADR using the `/to-adr` skill. Don't push it — a one-line offer is enough.

Create files lazily — only when there is something to write.