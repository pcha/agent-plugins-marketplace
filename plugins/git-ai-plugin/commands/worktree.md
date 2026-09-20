---
description: Create a Git worktree and optionally reproduce local setup
argument-hint: "<path> [branch-or-commit]"
---

Create a worktree without disturbing the current checkout.

1. Resolve the repository root and inspect existing worktrees. Confirm the requested destination is specific, outside the current worktree, and does not already exist.
2. Confirm whether the second argument is an existing branch, a commit/ref, or a new branch name. Ask only when the intended behavior changes the command.
3. Run the appropriate `git worktree add` form and verify the checked-out branch or commit.
4. If `.idea/` exists and is untracked or ignored, ask before copying it. If a root `CLAUDE.md` is untracked, ask before creating a relative symlink to it.
5. List other untracked files with `git ls-files --others --exclude-standard`. Never copy credentials, environment files, keys, build outputs, or other untracked content automatically; ask which explicit paths to copy, symlink, or skip.
6. Report the worktree path, checked-out ref, and any copied or linked setup.

Preserve file permissions. If setup after `git worktree add` fails, keep the valid worktree and explain what remains instead of deleting it automatically.
