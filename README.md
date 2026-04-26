# realtor-os-wiki

> 🔒 **PRIVATE.** Password-protected docs site for personal use only.
> Documents the upstream open-source repo
> [`puzzled-mushroom911/claude-code-real-estate-framework`](https://github.com/puzzled-mushroom911/claude-code-real-estate-framework)
> AS-IS. AI agents primary audience.

## Live Site

URL: TBD (Documentation.AI subdomain — set after Phase 4)
Access: password-protected (Documentation.AI Tier 3 feature)

## Quickstart

```bash
git clone git@github.com:tominhphong/realtor-os-wiki.git
cd realtor-os-wiki
bash scripts/pre-commit-check.sh
bash scripts/check-frontmatter.sh
bash scripts/check-links.sh
```

## Structure

| Folder | Owner | Purpose |
|---|---|---|
| `framework/` | Agent A | Architecture, principles, repo layout |
| `core-rules/` | Agent A | TREC, Fair Housing, content style, code conventions |
| `workflows/` | Agent B | Multi-step pipelines (1-video-5-assets, voice-cloning, …) |
| `agent-instructions/` | Agent B | 9 agent system prompts (paraphrased) |
| `mcp-tools/` | Agent C | 6 MCP tool groups (rag, youtube, content, crm, csv, guide) |
| `python-tools/` | Agent C | 6 Python tool categories |
| `frameworks/` | Agent D | Brunson / Hormozi / Channel Junkies (high-level paraphrase) |
| `knowledge-qa/` | Agent D | Glossary, tools catalog, MDX gotchas |
| `help-center/` | Agent D | Setup guide, troubleshooting, FAQ |
| `scripts/` | Brain | Validation scripts |
| `.github/workflows/` | Brain | CI pipeline |
| `plans/` | Brain | Sprint coordination |

## Convention

- Frontmatter mandatory — see `CLAUDE.md`
- Pre-commit gate before push — see `scripts/`
- File ownership strict — see `AGENTS.md` + `CODEOWNERS`

## Source

Upstream repo cloned at `~/Antigravity Workspace/projects/claude-code-real-estate-framework/`.
License: NULL (no explicit license). Personal/learning use only. Paraphrase frameworks; do NOT republish verbatim.
