# Domain Docs

How the engineering skills should consume this repo's domain documentation when exploring the codebase.

## Layout: single-context

This repo is **single-context**: one `CONTEXT.md` shared by the whole repository, with architecture decisions in `docs/adr/`. There is no `CONTEXT-MAP.md` and no per-subproject `CONTEXT.md`.

That holds even though the workspace root is an umbrella directory holding three sibling checkouts of the wiki (`jubeat-wiki/`, `jubeat-wiki-v2/`, `jubeat-wiki-v3/`): they are successive generations of one domain — the jubeat 音乐魔方 wiki — so they share one vocabulary rather than each owning a context. When a term or a decision genuinely crystallises, it is written once, at the root.

## Before exploring, read these

- **`CONTEXT.md`** at the repo root — the shared glossary and domain language.
- **`docs/adr/`** — read ADRs that touch the area you're about to work in.

If these files don't exist yet, **proceed silently**. Don't flag their absence; don't suggest creating them upfront. The `/domain-modeling` skill (reached via `/grill-with-docs` and `/improve-codebase-architecture`) creates them lazily when terms or decisions actually get resolved.

## File structure

```
Jubeat-wiki/                     ← workspace root, this repo (github.com/SnowindMe/jubeat-wiki)
├── CONTEXT.md                   ← created lazily, not yet present
├── AGENTS.md
├── docs/
│   ├── adr/                     ← system-wide decisions, at the root
│   └── agents/                  ← issue tracker / triage labels / this file
├── jubeat-wiki/                 ← v1 (sibling checkout, own git repo)
├── jubeat-wiki-v2/              ← v2 (sibling checkout, own git repo)
└── jubeat-wiki-v3/              ← v3, current development (sibling checkout, own git repo)
```

### Pre-existing, per-generation docs

Each generation already carries its own design history. Read them when working inside that generation, but treat them as **evidence**, not as the workspace-level domain doc:

- `jubeat-wiki-v1`: `jubeat-wiki/docs/*.md` (data contract, design system, feature decisions, environment pitfalls, …)
- `jubeat-wiki-v2`: `jubeat-wiki-v2/docs/*.md` (`requirements.md`, `design-system.md`, `PROJECT-NOTES.md`, `MEMO-FORMAT.md`, …)
- `jubeat-wiki-v3`: `jubeat-wiki-v3/jubeat-wiki-v3-context/docs/*.md` and its `docs/adr/0001-0006` (machine-data-read-only, dual-block-navigation, tiered-review, markdown-source-storage, prerendered-static-read-pages, self-hosted-accounts)

## Use the glossary's vocabulary

When your output names a domain concept (in an issue title, a refactor proposal, a hypothesis, a test name), use the term as defined in `CONTEXT.md`. Don't drift to synonyms the glossary explicitly avoids.

If the concept you need isn't in the glossary yet, that's a signal: either you're inventing language the project doesn't use (reconsider) or there's a real gap (note it for `/domain-modeling`).

## Flag ADR conflicts

If your output contradicts an existing ADR, surface it explicitly rather than silently overriding:

> _Contradicts ADR-0007 (event-sourced orders), but worth reopening because…_
