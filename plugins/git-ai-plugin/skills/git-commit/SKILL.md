---
name: git-commit
description: Create conventional Git commits and optionally push or open a pull request when the user asks to commit, commit and push, formulate a commit message, or commit current changes. Do not use for merely explaining Git concepts or reviewing a diff without a requested commit.
---

# Git Commit

Inspect the repository before mutating it: read status, staged and unstaged diffs, the current branch, and recent commit style. Keep unrelated user changes out of the commit; ask when scope cannot be inferred safely.

Use `type(scope): description` with an imperative, concise description. Supported types are `feat`, `fix`, `refactor`, `test`, `docs`, `chore`, `style`, `perf`, `ci`, and `build`. If the branch name contains a Jira key matching `[A-Z]+-[0-9]+`, add `Ticket: KEY-123` as the footer. Never add co-author or AI attribution lines.

Stage only intended files, run an appropriate lightweight validation plus `git diff --cached --check`, and review the staged diff. Use only `-m` options for the commit message and do not bypass hooks unless explicitly requested.

A request to commit does not authorize pushing. Push only when requested; use a normal push unless the user explicitly requests force, in which case use `--force-with-lease`. A requested PR implies pushing its branch but never merging the PR.
