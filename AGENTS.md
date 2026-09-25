# AGENTS.md

> 本文件面向在此仓库工作的 AI agent（Codex / Claude Code / DSH 等）。
> 本工作区根目录 `github.com/SnowindMe/jubeat-wiki` 是一个**伞状目录**，下面挂着 v1 / v2 / v3 三代站点的独立 checkout，各自是独立的 git 仓库；根仓库本身不装依赖、不构建。

## 仓库构成

| 路径 | 说明 | 包管理 |
| --- | --- | --- |
| `jubeat-wiki/` | v1，Svelte + Vite，早期版本 | npm |
| `jubeat-wiki-v2/` | v2，Astro 纯静态资料站 | npm |
| `jubeat-wiki-v3/` | v3，Astro + Cloudflare，**当前开发主线**；需求文档在其 `jubeat-wiki-v3-context/` | npm |
| `songjackets/` | 曲绘等静态资源 | — |

改动前先确认目标在哪一代目录里；跨代共用的结论写进根目录文档。

## Agent skills

### Issue tracker

Issues and specs live as GitHub issues in `SnowindMe/jubeat-wiki`, driven by the `gh` CLI. See `docs/agents/issue-tracker.md`.

### Triage labels

The five canonical triage roles use their own names as labels: `needs-triage`, `needs-info`, `ready-for-agent`, `ready-for-human`, `wontfix`; `/wayfinder` adds `wayfinder:map` and `wayfinder:research|prototype|grilling|task`. See `docs/agents/triage-labels.md`.

### Domain docs

single-context — one root `CONTEXT.md` plus `docs/adr/`, shared by all three generations. See `docs/agents/domain.md`.
