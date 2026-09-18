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

The line the skill holds is that two things make an answer yours: no fact can settle it, or being wrong costs more than a redo. The list above is the recurring cases rather than the boundary, and for anything it does not name the ADR test decides: hard to reverse, surprising without context, the result of a real trade-off. Hard to reverse is yours; cheap to reverse is the agent's. It asks in rounds shaped like grilling (numbered `❓` questions, each with a `➡️` recommendation) and waits, so a whole frontier of owner questions arrives at once and nothing depends on an answer still open.

The report is a **decision log**, weightiest decision first: **what** in one line, **why** with the rejected alternative, **how to undo it** and what would later make that expensive. It shows the load-bearing decisions working on one real case with real values, and marks the decision the agent is least sure of so you know where to push back. Under the log it lists the assumptions it did not ask about, and states what it deliberately left open and why that is cheaper to decide later.

## Common questions

**It asked me nothing and went straight to the report.**
That is legitimate where every call was genuinely cheap to reverse, and worth a second look where it was not. The check is the log itself: read the **how to undo** line on each entry, and the decision marked as the least sure one. If something there is expensive to reverse, or turns on money, legal exposure, who the product is for, or the quality bar, it was yours and it got settled silently. Say so and that one decision reopens.

**Does anything survive the session?**
No. The skill writes no files, and nothing it drafts is canon once the session ends unless you say so. When you want the decisions kept, run [draft-with-docs](https://aihero.dev/skills-draft-with-docs) instead: it runs the same session, then asks which decisions should outlive it and records only those as ADRs and glossary entries through [domain-modeling](https://aihero.dev/skills-domain-modeling).

**Can I switch to grilling halfway through?**
Yes, and the rounds are shaped alike so that you can: numbered questions, one recommendation each. Answer the round, then ask to be grilled on the branch you want to own yourself, and the format does not change under you. The usual reason is a call the skill ranked as its own that you would rather make.

**`draft-with-docs` ran, but it never loaded `drafting`.**
The same rough edge is reported for `grill-with-docs` across [harnesses](https://www.aihero.dev/ai-coding-dictionary/harness): a skill whose body names other skills does not reliably cause them to load, and `draft-with-docs` names two. The tell is a session that interviews you about libraries and file layout, which is a [model](https://www.aihero.dev/ai-coding-dictionary/model) improvising an interview rather than running this skill. Asking the agent directly whether it loaded `drafting` and `domain-modeling` usually recovers it.

## It's working if

- Every question you get is one of the owner's questions above, never "which library".
- Each question arrives numbered with a recommendation, and you can answer the round by number.
- Every entry in the report has three labelled lines, and "how to undo" says *trivial* where it is.
- The rejected option is in the report next to the one that was picked.
- The report names the decision the agent is least sure of, or says plainly that none of them is shaky.

## Where it fits

`drafting` is the primitive beside [grilling](https://aihero.dev/skills-grilling): grilling interviews you for the decisions, drafting makes them for you and puts to you only the owner's questions. [draft-with-docs](https://aihero.dev/skills-draft-with-docs) wraps it the way [grill-with-docs](https://aihero.dev/skills-grill-with-docs) wraps grilling, and [wayfinder](https://aihero.dev/skills-wayfinder) types its tickets by the same split. For anything else, [ask-matt](https://aihero.dev/skills-ask-matt) routes over the whole set.
