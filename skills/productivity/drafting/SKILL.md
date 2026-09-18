---
name: drafting
description: Draft a design yourself - research the facts, make the technical calls, explain each one, and put to the user only what they alone can answer. Use when the user wants the design worked out for them instead of being interviewed about it.
---

# Drafting

Work the design out yourself and present it.
The user is the owner, not the domain expert - do not interview them as if the knowledge were theirs to supply.
Nothing is canon when the session ends unless they say so.

## Own the work

Find the facts yourself: the codebase, `CONTEXT.md`, the ADRs, and primary sources (call the Skill tool with "research" for anything that needs reading outside the repo).
Never ask the user for something you could look up.
If what you find kills the premise - the codebase already solves this another way, or a fact makes the approach impossible - stop and report that, instead of designing around it.

Then make the calls you are more competent to make: libraries and tools, file layout, schema and interface details, error handling, test strategy, naming inside the code, algorithms, the order of the work.
Design it twice before you settle - carry the option you rejected into the report, not only the one you picked.

## Escalate only what is theirs

Put a question to the user only when the answer is theirs as the accountable owner, never as an expert.
Two things make an answer theirs: no fact can settle it, or being wrong costs more than a redo.
The shapes this takes, over and over:

- money, vendor lock-in, anything with a bill attached
- legal, regulatory and personal-data exposure
- who the product is for, and what you are deliberately NOT building
- the quality bar - latency, uptime, audit trail, what is allowed to fail
- anything expensive to reverse once real data or a partner depends on it
- genuine ties, where the options are equal and it comes down to their taste

The list is the recurring cases, not the boundary.
For anything it does not name, the ADR test decides: hard to reverse, surprising without context, the result of a real trade-off.
Hard to reverse is theirs; cheap to reverse is yours.

Ask in numbered rounds, in the same shape as grilling, so the two skills compose:

```
❓ **Q1** - **<decision at stake>**: <what hangs on it, and the options with their cost>

➡️ <your recommended answer and its main trade-off>

---

❓ **Q2** - **<decision at stake>**: <what hangs on it, and the options with their cost>

➡️ <your recommended answer and its main trade-off>
```

Put the whole frontier of owner questions in one round, then wait; a question whose answer depends on another still open belongs to the next round.
Settle a decision only after its answer is in.
The rounds are done when no owner question is left open; then report.

## Report

Present the draft as a decision log. Each decision is three separate labelled lines:

- **What** you settled on, in one line.
- **Why** - the trade-off, and what you rejected.
- **How to undo it** if it turns out wrong, and what would later make it expensive.
  When the reversal is genuinely free, write "trivial" - never invent a cost - and ask yourself whether the decision belongs in the log at all.

Order the decisions by consequence, the weightiest first - the reader stops reading when it stops mattering.
Report only the decisions that carry the design; leave the minor calls out entirely - the report is for reading, not for the record.
Show the load-bearing decisions working on one real case, with real values, rather than describing them in the abstract.
Mark the decision you are least sure of, so the reader knows where to push back; where none of them is shaky, say that instead of manufacturing a doubt.

List the assumptions the draft rests on: the things you were confident enough not to ask about.
Then state what you deliberately left open, and why it is cheaper to decide later.
