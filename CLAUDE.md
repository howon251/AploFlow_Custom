# AploFlow_Custom

Custom scripts and software for the Aplo Flow system, with a user manual for each tool.

## Structure
- `src/`  : scripts and software (one folder per tool, e.g. `src/flush_test/`)
- `docs/` : user manuals in Markdown, one file per tool (e.g. `docs/flush_test.md`)
- `.claude/agents/` : role-specific agents (added later)
- `.claude/skills/` : repeatable procedures (added later)

## Rules
- When a tool's behavior, arguments, or output changes, update its manual in `docs/` in the same commit.
- Every new tool gets a manual created from `docs/_template.md`.
- Manuals are written in concise, natural English.
- Commit messages: `[tool-name] short summary of the change`.
- Never commit customer data, credentials, or instrument serial numbers.

## Workflow
1. Code in VS Code with Claude Code → commit (code + manual) → push.
2. In the Claude app Project, press **Sync now** to review and polish manuals.
3. Edits made in the app come back as a pull request → merge → `git pull`.
