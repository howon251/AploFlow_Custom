# AploFlow_Custom

Custom scripts and software for the Aplo Flow system, with a user manual for each tool.

## Structure
- `specs/`: work definitions written in the Claude app, one file per tool or project (e.g. `specs/flush_test.md`)
- `src/`  : scripts and software (one folder per tool, e.g. `src/flush_test/`)
- `docs/` : user manuals in Markdown, one file per tool (e.g. `docs/flush_test.md`)
- `.claude/agents/` : role-specific agents (added later)
- `.claude/skills/` : repeatable procedures (added later)

## Rules
- Before starting any new tool or project, read its spec in `specs/`. If no spec exists, ask for one before writing code.
- Treat the spec as the source of truth. If implementation needs to differ from it, stop and ask, then update the spec in the same commit as the change.
- When the work is finished, set the spec's Status to Done and tick the "Done when" checklist.
- When a tool's behavior, arguments, or output changes, update its manual in `docs/` in the same commit.
- Every new tool gets a manual created from `docs/_template.md`.
- Manuals are written in concise, natural English.
- Commit messages: `[tool-name] short summary of the change`.
- Never commit customer data, credentials, or instrument serial numbers.

## Workflow
0. Define the work in the Claude app → save it as `specs/<name>.md` from `specs/_template.md` → merge the PR.
1. In VS Code: `git pull`, then ask Claude Code to "read specs/<name>.md and implement it".
2. Implement in VS Code with Claude Code → commit (code + manual) → push.
3. In the Claude app Project, press **Sync now** to review and polish manuals.
4. Edits made in the app come back as a pull request → merge → `git pull`.
