## What it does

`draft-with-docs` runs a [drafting](https://aihero.dev/skills-drafting) session (the [agent](https://www.aihero.dev/ai-coding-dictionary/agent) works the design out, puts to you only the owner's questions, and reports a decision log) and then asks which of those decisions should outlive the [session](https://www.aihero.dev/ai-coding-dictionary/session). The ones you pick are written into the repo with [domain-modeling](https://aihero.dev/skills-domain-modeling); the rest leave no trace.

That last step is the difference from [grill-with-docs](https://aihero.dev/skills-grill-with-docs), which records as it goes. A draft is the agent's proposal, so nothing in it is canon until you say so: the paper trail is written after the selection, not during the interview.

## When to reach for it

You invoke this by typing `/draft-with-docs`; the agent won't reach for it on its own.

Reach for it in a repo, at the start of a change you want worked out for you instead of being interviewed about. For a change you want to settle by interview, use [grill-with-docs](https://aihero.dev/skills-grill-with-docs) instead.

| What you have | Reach for |
| --- | --- |
| A repo, and a change you want worked out for you | `draft-with-docs` |
| A repo, and a change you want to settle by interview | [grill-with-docs](https://aihero.dev/skills-grill-with-docs) |
| An effort too big for one session | [wayfinder](https://aihero.dev/skills-wayfinder), which types each ticket as grilling or drafting |

## Prerequisites

It writes into your repo: resolved terms go to `CONTEXT.md`, decisions that pass the ADR gates go to `docs/adr/`, both created lazily. Its `SKILL.md` delegates to [drafting](https://aihero.dev/skills-drafting) and [domain-modeling](https://aihero.dev/skills-domain-modeling), so both must be installed.

## The selection

When the decision log is on the table the skill asks, one option per decision and multi-select, which decisions should outlive the session. Only those are handed to domain-modeling: a term lands in `CONTEXT.md`; a decision that is hard to reverse, surprising without context and a real trade-off lands as an ADR. Everything you did not select stays in the conversation.

## It's working if

- You were asked only the owner's questions during the draft, and the selection afterwards.
- `CONTEXT.md` and `docs/adr/` change only after you picked, and only for what you picked.
- The ADRs that appear are decisions you would be annoyed to re-litigate.

## Where it fits

`draft-with-docs` is the drafting-side head of the main chain, beside [grill-with-docs](https://aihero.dev/skills-grill-with-docs):

```txt
draft-with-docs → to-spec → to-tickets → implement → code-review
```

It sits on [drafting](https://aihero.dev/skills-drafting) the way grill-with-docs sits on [grilling](https://aihero.dev/skills-grilling); [domain-modeling](https://aihero.dev/skills-domain-modeling) is the writing discipline both drive. When you're unsure which skill or flow fits, [ask-matt](https://aihero.dev/skills-ask-matt) routes you.
