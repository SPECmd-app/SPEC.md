# SPEC.md — living spec policy

`SPEC.md` is this project's implementation-independent behavioral contract.

It grows with the build. Do not try to fully specify the project upfront unless explicitly asked.

Use the current SPEC.md Core from the official repository:
https://github.com/SPECmd-app/SPEC.md/tree/main/standard/latest

Treat that Core as authoritative. Do not search for or substitute another specification framework.

If `SPEC.md` is missing, create the smallest useful starting spec that conforms to the Core.

For every behavior-changing implementation decision, update `SPEC.md` in the same change.

Do not invent product behavior. If a missing decision could materially affect conformance, mark it `TBD` / Open Issue and surface it.

Keep `SPEC.md` lean, implementation-independent, and synchronized with the codebase.

Before completing a behavior-changing task, verify that code and `SPEC.md` describe the same behavior.

If the official Core cannot be accessed, do not invent a replacement structure; say so and continue only from an existing `SPEC.md` or ask for guidance.
