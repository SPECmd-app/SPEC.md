# SPEC.md

**Portable Ideas and Designs.**

> Source code is one implementation of an idea.
> SPEC.md is the transferable expression of the idea itself.

- **Share the design, not just the code.** Capture the core of a design, how it should behave, and what must remain true independently of any particular implementation.
- **Build it anywhere.** A SPEC.md can be understood and implemented by different people, teams, technologies, or LLMs without access to the original codebase.
- **Make great ideas reusable.** SPEC.md is an open, human-readable format for describing systems, products, workflows, and designs so they can be studied, shared, adapted, and independently recreated.

SPEC.md is an open format for expressing ideas and designs independently of how they are implemented. It captures the behavior, rules, constraints, relationships, and decisions that define a system, while leaving the implementation free to use different technologies, architectures, and environments.

The goal is simple: make great designs portable. A SPEC.md should be understandable on its own, so another person or LLM can take the specification and create a conforming implementation without access to the original source code or hidden project knowledge.

📖 **[Read the site](https://specmd-app.github.io/SPEC.md/)** — rendered docs, the versioned standard, worked examples, and coding-agent integrations.

## Repo layout

```
docs/           the published site (GitHub Pages source): homepage and the
                versioned standard (0.2.0 → 0.4.2)
examples/       one worked example ("Judo Club Website") at each standard version
integrations/   drop-in CLAUDE.md / AGENTS.md prompts that keep a project's SPEC.md
                up to date as a coding agent builds it
```

The latest version is **[0.4.2](docs/standard/0.4.2.md)** (plus its optional companion, [`0.4.2-optional.md`](docs/standard/0.4.2-optional.md)); `docs/standard/latest/` always redirects to whichever version is current.

See [`CHANGELOG.md`](CHANGELOG.md) for what changed in each version.

## License

[Apache-2.0](LICENSE)
