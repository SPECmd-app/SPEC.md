# Changelog

Notable changes to the SPEC.md standard. Each entry covers `docs/standard/<version>.md` (SPEC.md Core) and, where relevant, its Optional companion.

## 0.4.3

Clarification release focused on how stable semantic IDs interact with traceability. No Core structure or required behavior was changed.

- **Added (Core):** Stable IDs may also identify non-requirement elements such as behavioral flows. An ID alone does not make an element normative — when traceability is used, TRACE coverage follows normative obligations, not every label in the document.
- **Clarified (Optional, flow identifiers):** A flow identifier identifies a behavioral flow; a flow ID does not by itself make the flow a normative requirement.
- **Clarified (Optional, TRACE.md):** A semantic ID does not by itself make an element a normative requirement. Behavioral flows and other identified elements MAY be traced when useful, but their IDs do not automatically require TRACE coverage.
- **Clarified (Optional, example trace chain):** A flow may appear in a trace chain because it helps explain how a requirement is realized, without implying every identified flow requires a TRACE.md entry.

**Compatibility:** a specification conforming to 0.4.2 should remain conforming to 0.4.3, unless tooling previously treated every ID-shaped label as a mandatory normative trace target — tools should classify identifiers by semantic role rather than by identifier syntax alone.

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
