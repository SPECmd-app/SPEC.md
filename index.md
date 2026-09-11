---
title: SPEC.md
---

# SPEC.md

**Portable Ideas and Designs.**

> Source code is one implementation of an idea.
> SPEC.md is the transferable expression of the idea itself.

## Main messages

- **Share the design, not just the code.** Capture the core of a design, how it should behave, and what must remain true independently of any particular implementation.
- **Build it anywhere.** A SPEC.md can be understood and implemented by different people, teams, technologies, or LLMs without access to the original codebase.
- **Make great ideas reusable.** SPEC.md is an open, human-readable format for describing systems, products, workflows, and designs so they can be studied, shared, adapted, and independently recreated.

## Brief summary

SPEC.md is an open format for expressing ideas and designs independently of how they are implemented. It captures the behavior, rules, constraints, relationships, and decisions that define a system, while leaving the implementation free to use different technologies, architectures, and environments.

The goal is simple: make great designs portable. A SPEC.md should be understandable on its own, so another person or LLM can take the specification and create a conforming implementation without access to the original source code or hidden project knowledge.

**Latest version: [0.4.2](standard/0.4.2.md)** &nbsp;·&nbsp; [stable "latest" link](standard/latest)

## The standard

| Version | Status |
| --- | --- |
| [0.4.2](standard/0.4.2.md) | Current |
| [0.4.1](standard/0.4.1.md) | Superseded |
| [0.3.0](standard/0.3.0.md) | Superseded |
| [0.2.0](standard/0.2.0.md) | Superseded |

**[SPEC.md Optional 0.4.2](standard/0.4.2-optional.md)** — companion document of optional extensions, authoring patterns, and companion artifacts. Nothing in it is required for Core conformance; use only what materially helps a given project.

See [`CHANGELOG.md`](CHANGELOG.md) for what changed in each version.

## Worked example

A single project ("Judo Club Website") specified at each stage of the standard's own evolution, so you can see how the same design reads under different versions:

- [SPEC.md 0.2.0](examples/judo-club-specmd-0.2.0.md)
- [SPEC.md 0.3.0](examples/judo-club-specmd-0.3.0.md)
- [SPEC.md 0.4.1](examples/judo-club-specmd-0.4.1.md)
- [SPEC.md 0.4.2](examples/judo-club-specmd-0.4.2.md)

## Living-spec integrations

Drop-in instructions that teach a coding agent to keep a project's `SPEC.md` up to date as it builds:

- **Claude Code** — [`CLAUDE.md`](integrations/claude-code/CLAUDE.md), [prompt reference](integrations/claude-code/SPECMD_CLAUDE_CODE_PROMPT.csv)
- **Codex** — [`AGENTS.md`](integrations/codex/AGENTS.md), [prompt reference](integrations/codex/SPECMD_CODEX_PROMPT.csv)

## License

[Apache-2.0](LICENSE)
