## What it does

`drafting` works a design out for you instead of interviewing you about it. The [agent](https://www.aihero.dev/ai-coding-dictionary/agent) finds the facts (the codebase, `CONTEXT.md`, the ADRs, [primary sources](https://www.aihero.dev/ai-coding-dictionary/primary-source)), makes the technical calls it is better placed to make, and presents the result as a **decision log**: for each decision, what was settled, why, and how to undo it.

It puts a question to you only when the answer is yours as the accountable owner, never as an expert: money and vendor lock-in, legal and personal-data exposure, who the product is for and what is deliberately not built, the quality bar, anything expensive to reverse, and genuine ties. Everything else it settles itself, and it carries the rejected option into the report. Nothing it drafts is canon when the [session](https://www.aihero.dev/ai-coding-dictionary/session) ends unless you say so.

## When to reach for it

Type `/drafting`, or the agent reaches for it on its own when you ask for a design to be worked out rather than discussed. Usually a skill you typed is running it: [draft-with-docs](https://aihero.dev/skills-draft-with-docs) is the named way in, and [wayfinder](https://aihero.dev/skills-wayfinder) runs it inside its `drafting` tickets.

What you are asking for decides between the two primitives:

| What you want | Reach for |
| --- | --- |
| To be interviewed until the decisions are yours | [grilling](https://aihero.dev/skills-grilling) |
| The design worked out for you, with only the owner's questions put to you | `drafting` |
| Answers from someone else's head | [to-questionnaire](https://aihero.dev/skills-to-questionnaire) |

## The owner's questions and the decision log

The line the skill holds is the ADR test: hard to reverse, surprising without context, the result of a real trade-off. Hard to reverse is yours; cheap to reverse is the agent's. It asks in rounds shaped like grilling (numbered `❓` questions, each with a `➡️` recommendation) and waits, so a whole frontier of owner questions arrives at once and nothing depends on an answer still open. Reaching the report without a single question is treated as a warning sign that an owner's call was settled silently.

The report is a **decision log**, weightiest decision first: **what** in one line, **why** with the rejected alternative, **how to undo it** and what would later make that expensive. It shows the load-bearing decisions working on one real case with real values, lists the assumptions it did not ask about, and states what it deliberately left open and why that is cheaper to decide later.

## It's working if

- Every question you get is one of the owner's questions above, never "which library".
- Each question arrives numbered with a recommendation, and you can answer the round by number.
- Every entry in the report has three labelled lines, and "how to undo" says *trivial* where it is.
- The rejected option is in the report next to the one that was picked.

## Where it fits

`drafting` is the primitive beside [grilling](https://aihero.dev/skills-grilling): grilling interviews you for the decisions, drafting makes them for you and puts to you only the owner's questions. [draft-with-docs](https://aihero.dev/skills-draft-with-docs) wraps it the way [grill-with-docs](https://aihero.dev/skills-grill-with-docs) wraps grilling, and [wayfinder](https://aihero.dev/skills-wayfinder) types its tickets by the same split. For anything else, [ask-matt](https://aihero.dev/skills-ask-matt) routes over the whole set.
