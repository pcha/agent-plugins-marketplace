---
name: git-worktree
description: Create and configure Git worktrees when the user asks for a parallel checkout, worktree, or isolated branch directory. Do not use for ordinary branch creation inside the current checkout.
---

# Git Worktree

Resolve the repository root and existing worktrees first. Require a specific destination outside the current worktree that does not already exist. Determine whether the requested ref is an existing branch, commit, or new branch before choosing the `git worktree add` form.

After creation, verify the resulting path and checked-out ref. Local editor settings or untracked project context may be reproduced only with user approval. Never automatically copy secrets, `.env` files, credentials, keys, build outputs, or arbitrary untracked content. Prefer relative symlinks for explicitly approved shared files.

If optional setup fails after the worktree itself was created, preserve the valid worktree and report the incomplete setup instead of deleting it.
