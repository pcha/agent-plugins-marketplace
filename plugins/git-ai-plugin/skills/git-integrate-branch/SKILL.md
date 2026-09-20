---
name: git-integrate-branch
description: Merge or rebase Git branches, analyze divergence, and guide conflict resolution when the user asks to integrate, merge, update, or rebase a branch. Do not use for routine pulls with no branch-integration request.
---

# Git Branch Integration

Identify the current branch, target, operation mode, merge base, unique commits, files changed on each side, and overlap before starting. Refuse to begin over an unresolved Git operation, and stop when unrelated local changes could be overwritten.

Fetch the relevant remote ref when needed, without checking out and pulling another local branch. Use merge by default and rebase only when requested or clearly established by repository workflow. Do not push as part of integration unless separately requested.

If conflicts occur, inspect all conflicts and commit intent before proposing edits. Group them into patterns and present one comprehensive resolution plan with tradeoffs. Wait for user approval before resolving. Never discard changes, abort an operation, or select ours/theirs wholesale without authorization.

After resolution, ensure conflict markers are gone, run `git diff --check`, complete the operation, and execute relevant project tests or checks. Report failures and remaining state clearly.
