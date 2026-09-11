---
title: SPEC.md
---

# SPEC.md

**Portable Ideas and Designs.**

> Source code is one implementation of an idea.
> SPEC.md is the transferable expression of the idea itself.

`SPEC.md` is an open, Markdown-based standard for expressing an idea, design, system, behavior, or rule set independently of any particular implementation — so a competent human or LLM, without access to the original source, can independently build a conforming implementation from the spec alone.

**Latest version: [0.3.0](standard/0.3.0.md)** &nbsp;·&nbsp; [stable "latest" link](standard/latest)

## The standard

| Version | Status |
| --- | --- |
| [0.3.0](standard/0.3.0.md) | Current |
| [0.2.0](standard/0.2.0.md) | Superseded |
| [0.1.0](standard/0.1.0.md) | Superseded |

## Worked example

A single project ("Judo Club Website") specified at each stage of the standard's own evolution, so you can see how the same design reads under different versions:

- [0.1.0](examples/judo-club-0.1.0.md)
- [0.1.0, revised](examples/judo-club-0.1.0-revised.md)
- [0.1.1](examples/judo-club-0.1.1.md)
- [SPEC.md 0.2.0](examples/judo-club-specmd-0.2.0.md)
- [SPEC.md 0.3.0](examples/judo-club-specmd-0.3.0.md)

## Living-spec integrations

Drop-in instructions that teach a coding agent to keep a project's `SPEC.md` up to date as it builds:

- **Claude Code** — [`CLAUDE.md`](integrations/claude-code/CLAUDE.md), [prompt reference](integrations/claude-code/SPECMD_CLAUDE_CODE_PROMPT.csv)
- **Codex** — [`AGENTS.md`](integrations/codex/AGENTS.md), [prompt reference](integrations/codex/SPECMD_CODEX_PROMPT.csv)

## License

[MIT](LICENSE)
