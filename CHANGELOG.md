# Changelog

Notable changes to the SPEC.md standard. Each entry covers `docs/standard/<version>.md` (SPEC.md Core) and, where relevant, its Optional companion.

## 0.4.2

Small clarification release focused on preventing over-design while preserving the living-spec model. No new Core section or optional framework was added.

- **Added:** "SPEC.md captures design decisions; it does not complete the design."
- **Added:** Assumptions, common practice, and likely future needs should not be turned into requirements.
- **Clarified:** Create `TBD` / Open Issues when the current design depends on an unresolved decision, not as a speculative future backlog.
- **Clarified non-goals:** A non-goal says what the spec does not require; it does not automatically forbid an implementation from doing more.
- **Updated agent prompts:** New features or behavior proposed by the agent should be suggested first and added to `SPEC.md` only after user approval.

## 0.4.1

Rebranded "SPEC.md Standard" to **SPEC.md Core**, formally separating the minimal Core standard from the SPEC.md Optional companion. Added the `SPECMD-HUMAN-ONLY` comment convention to Core.

## 0.3.0

Promoted the material-ambiguity test into Core and defined root-owned versioning for modular Specification Sets.

## 0.2.0

Earlier draft of the standard. See [`docs/standard/0.2.0.md`](docs/standard/0.2.0.md).
