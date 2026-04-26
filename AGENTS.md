# AGENTS.md — realtor-os-wiki

Multi-agent file ownership map for parallel content generation. 4 Task subagents work concurrently in same git branch. Strict scope = zero merge conflicts.

## Brain (Main Session)

- Owns: `documentation.json`, top-level pages (`introduction.mdx`, `quickstart.mdx`), `plans/`, `scripts/`, `.github/workflows/`
- Consolidates nav after all 4 subagents return
- Single instance, sequential

## Agent A — Framework + Core Rules

- Owns: `framework/`, `core-rules/`
- Reads from upstream: `README.md`, `DESKTOP-SETUP.md`, `.claude/rules/*.md`, `config/`
- Output: 10 pages

## Agent B — Workflows + Agent Instructions

- Owns: `workflows/`, `agent-instructions/`
- Reads from upstream: `.claude/agents/*.md` (9 files), `examples/`, `templates/`
- Output: 14 pages

## Agent C — MCP Tools + Python Tools

- Owns: `mcp-tools/`, `python-tools/`
- Reads from upstream: `mcp_server/src/tools/*.ts`, `tools/*/`
- Output: 12 pages

## Agent D — Frameworks + Knowledge-QA + Help-Center

- Owns: `frameworks/`, `knowledge-qa/`, `help-center/`
- Reads from upstream: `knowledge_bases/prompts/*.md` (paraphrase frameworks ONLY, NO verbatim books)
- Output: 10 pages

## Rules

1. Subagent edits outside owned folder = ABORT
2. Subagent does NOT edit `documentation.json` — Brain only
3. All pages use 7-field frontmatter (see CLAUDE.md)
4. All pages reference source file in upstream repo (e.g., "Source: `.claude/agents/email-writer.md`")
5. Cross-references use `/folder/page` (no `.mdx` suffix)
6. Run `bash scripts/pre-commit-check.sh` before commit
