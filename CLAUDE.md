# CLAUDE.md — realtor-os-wiki

> Private docs site documenting the upstream open-source repo
> `puzzled-mushroom911/claude-code-real-estate-framework` AS-IS.
> AI agents primary audience. Phong secondary.

## Scope

- **Document the upstream repo** — agents, skills, rules, MCP tools, Python tools, prompts, templates, scripts
- **Paraphrase only** — high-level concepts from Brunson / Hormozi / Channel Junkies. NEVER reproduce verbatim book text. Cite original on every framework page.
- **English only** — no bilingual content
- **No personal playbook** — this site is reference for the framework, not Phong's case study

## Out of Scope

- Phong's customizations of the framework (those live in private notes / Agent OS)
- Course material / SaaS productization
- Vietnamese-language content
- Marketing copy

## Frontmatter (mandatory on every .mdx)

```yaml
title: "..."           # 3-80 chars
description: "..."     # 50-200 chars
last_reviewed: YYYY-MM-DD
type: overview | reference | workflow | protocol | example | decision | changelog
audience: ai-agent-primary | both | phong-review
use_case: [kebab-case-verbs]
keywords: [searchable terms]
```

Validator: `bash scripts/check-frontmatter.sh`

## Pre-commit Gate (always run before push)

```bash
bash scripts/pre-commit-check.sh
bash scripts/check-frontmatter.sh
bash scripts/check-links.sh
```

CI pipeline (`.github/workflows/mdx-validate.yml`) runs all 3 + stale check. PR blocked if any fail.

## File Ownership (multi-agent sessions)

See `AGENTS.md` for Agent A/B/C/D scope map and `CODEOWNERS` for path enforcement.

## MDX Gotchas (top 5)

1. No `<[digit]` (JSX collision) — escape as `&lt;[`
2. No HTML comments `<!-- -->` — use `{/* JSX */}`
3. No Mermaid (unsupported) — use ASCII or PNG
4. Pipe `|` inside JSX attribute in markdown table → escape or restructure
5. Asterisks inside `<text>` SVG — escape as `&#42;`

Full list: `knowledge-qa/mdx-gotchas` (Phase 2 Agent D).

## Source Repo Reference

Upstream cloned at `~/Antigravity Workspace/projects/claude-code-real-estate-framework/`. License: NULL — personal/learning use only. Do NOT republish verbatim agents/skills MD files; rephrase + add own notes.
