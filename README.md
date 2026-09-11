# SPEC.md

**Portable Ideas and Designs.**

`SPEC.md` is an open, Markdown-based standard for expressing an idea, design, system, behavior, or rule set independently of any particular implementation — so a competent human or LLM, without access to the original source, can independently build a conforming implementation from the spec alone.

📖 **[Read the site](https://specmd-app.github.io/SPEC.md/)** — rendered docs, the versioned standard, worked examples, and coding-agent integrations.

## Repo layout

```
standard/       the versioned SPEC.md standard itself (0.1.0 → 0.3.0)
examples/       one worked example ("Judo Club Website") at each standard version
integrations/   drop-in CLAUDE.md / AGENTS.md prompts that keep a project's SPEC.md
                up to date as a coding agent builds it
```

The latest version is **[0.3.0](standard/0.3.0.md)** (plus its optional companion, [`0.3.0-optional.md`](standard/0.3.0-optional.md)); `standard/latest/` always redirects to whichever version is current.

## License

[Apache-2.0](LICENSE)
