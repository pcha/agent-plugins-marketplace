---
description: Create a conventional commit with optional push or pull request
argument-hint: "[--push|-p] [--force|-f] [--pr]"
---

Create a conventional commit from the intended working-tree changes. Parse `$ARGUMENTS` for `--push`/`-p`, `--force`/`-f`, and `--pr`; combined short flags such as `-pf` are valid. `--pr` implies push.

1. Inspect `git status`, staged and unstaged diffs, the current branch, and recent commit style. Do not include unrelated user changes. If the intended scope is ambiguous, ask before staging.
2. Extract a Jira key matching `[A-Z]+-[0-9]+` from the branch name when present.
3. Choose a concise imperative Conventional Commit message: `type(scope): description`. Allowed types are `feat`, `fix`, `refactor`, `test`, `docs`, `chore`, `style`, `perf`, `ci`, and `build`.
4. Stage the intended files. Use `git add .` only when all current changes are in scope.
5. Run an appropriate lightweight validation and `git diff --cached --check`, then review the staged diff.
6. Commit using only `-m` options. Add `Ticket: TICKET-123` as a footer when a Jira key was found. Never add co-author or AI attribution lines, and never bypass hooks unless the user explicitly asks.
7. Push only when requested. Use a normal `git push` unless both push and force were requested; then use `git push --force-with-lease`, never plain `--force`.
8. If `--pr` was supplied, create a PR only after a successful push by following the PR workflow. Do not merge it.

Report the commit hash, validation performed, and any remote action.
