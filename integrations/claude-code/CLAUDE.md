# SPEC.md — living spec policy

`SPEC.md` is this project's implementation-independent behavioral contract.

It grows with the build. Do not try to fully specify the project upfront unless explicitly asked.

Use SPEC.md Core 0.4.2:
https://raw.githubusercontent.com/SPECmd-app/SPEC.md/main/docs/standard/0.4.2.md

Treat this Core file as authoritative. Do not search for or substitute another specification framework. Do not load SPEC.md Optional unless the project explicitly needs an optional extension.

If `SPEC.md` is missing, create the smallest useful starting spec that conforms to the Core.

Whenever you implement, change, or decide behavior, update `SPEC.md` in the same change.

If you think the product needs a new feature or behavior, suggest it first. Add it to `SPEC.md` only after the user agrees. If the user has already decided it, capture it directly.

Do not turn assumptions, common practice, or likely future needs into requirements.

If a missing decision could materially affect conformance, mark it `TBD` / Open Issue and surface it. Do not create future Open Issues merely because a decision may become relevant later.

Keep `SPEC.md` lean, implementation-independent, and synchronized with the implementation.

Before finishing a behavior-changing task, confirm that the implementation and `SPEC.md` describe the same behavior.

If the Core file cannot be accessed, do not invent a replacement structure; continue only from an existing `SPEC.md` or ask for guidance.
