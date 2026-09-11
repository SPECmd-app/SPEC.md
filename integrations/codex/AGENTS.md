# SPEC.md — living spec, grows with the build

`SPEC.md` is this project's implementation-independent behavioral contract.

It is not written upfront. Build it incrementally, in lockstep with implementation.

This policy applies repo-wide unless a more specific `AGENTS.md` explicitly refines it for a subtree. A nested instruction MUST NOT weaken the authority of the root `SPEC.md` over project behavior unless the root specification explicitly allows that scope to differ.

## Bootstrap

If `SPEC.md` is missing, create it before or as part of the first behavior-changing implementation work.

Start with:

```yaml
---
specmd: "0.3.0"
spec_version: "0.1.0"
status: draft
---
```

Add a short **Specification Contract** stating that:

- uppercase `MUST`, `MUST NOT`, `SHOULD`, `SHOULD NOT`, and `MAY` use BCP 14 semantics;
- `SPEC.md` is authoritative for required behavior when it conflicts with implementation code or implementation documentation;
- an unspecified internal detail that cannot materially affect conformance MAY be chosen by the implementer;
- an omission or ambiguity that could materially affect externally observable behavior, data semantics, security, privacy, accessibility, interoperability, safety, or another normative property MUST be surfaced rather than silently resolved;
- genuinely undecided behavior is marked `TBD` / Open Issue and is never guessed.

Create these Core sections, initially empty except where current project facts are already known:

1. Overview and Scope
2. Context and Definitions
3. System Model
4. Requirements
5. Interfaces and External Contracts
6. Constraints and Non-Goals
7. Verification and Acceptance
8. Notes and Rationale

Do not invent content merely to fill sections.

## Living-spec rule

Whenever you implement, change, or decide user-facing or system behavior, update `SPEC.md` in the same patch.

Do not defer specification work until the end.

Before finishing a behavior-changing task, verify that the corresponding normative requirement is present and current.

Add or update the smallest matching normative requirement.

Requirements must be:

- atomic;
- normative;
- implementation-independent;
- explicit about defaults where omission could produce materially different behavior;
- explicit about deliberate prohibitions and exclusions;
- verifiable where practical.

Do not name frameworks, libraries, source files, database mechanisms, or internal architecture unless that choice is itself a required constraint.

When the first normative requirement is added, assign stable semantic IDs such as:

- `FUN-001`
- `DATA-001`
- `AUTH-001`
- `INT-001`
- `SEC-001`

Keep requirement IDs stable when requirements move. Never reuse retired IDs.

Deliberate exclusions belong in **Constraints and Non-Goals** rather than being left implicit.

Behaviorally significant features should include a short `Given / When / Then` acceptance note where that makes verification clearer.

Rationale, history, alternatives, and implementation advice belong in **Notes and Rationale** and are informative unless explicitly marked normative.

## Existing SPEC.md

If `SPEC.md` already exists:

1. read it before making behavior-changing implementation decisions;
2. preserve its terminology and requirement IDs;
3. do not silently reinterpret or weaken existing normative requirements;
4. update the relevant requirement in the same patch as the behavior change;
5. surface material contradictions between the requested change and the existing specification.

Implementation code is not a source of authority over an existing normative requirement.

## Versioning

Bump `spec_version` whenever the specification changes:

- **MAJOR** — a previously conforming implementation may become non-conforming;
- **MINOR** — additive behavior that preserves previous conformance;
- **PATCH** — clarification or editorial change with no normative behavioral difference.

A code-only refactor that does not alter specified behavior does not require a `spec_version` bump.

When behavior changes and `SPEC.md` changes in the same patch, determine the version bump from the specification change, not from the size of the code diff.

## Ambiguity policy

If the specification leaves an internal implementation choice open and that choice cannot materially affect conformance, choose an appropriate implementation and continue.

If the missing decision could materially affect required behavior, data semantics, security, privacy, accessibility, interoperability, safety, or another normative property:

1. add a `TBD` / Open Issue to `SPEC.md`;
2. surface the ambiguity clearly;
3. do not invent product or design behavior merely to unblock implementation.

## Verification

For behavior-changing work:

- update or add verification/acceptance criteria where appropriate;
- run the project's relevant tests and checks;
- ensure the implemented behavior and `SPEC.md` describe the same contract before considering the task complete.

`SPEC.md` should grow as a durable side effect of building the project.
