---
"mattpocock-skills": minor
---

Add `drafting` and `draft-with-docs`, and give `wayfinder` a drafting ticket type.

- `drafting` (productivity, model-invoked): the agent works the design out itself (finds the facts, makes the technical calls, carries the rejected option) and puts to the user only the owner's questions, in grilling-shaped rounds; the report is a decision log (what / why / how to undo).
- `draft-with-docs` (engineering, user-invoked): a drafting session that then asks which decisions outlive it and records those with `domain-modeling`.
- `wayfinder`: a fifth ticket type, `drafting`, for a ticket the human wants worked out for them instead of being interviewed about, resolved by `drafting` plus `domain-modeling`; `grilling` stays the default.
