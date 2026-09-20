---
description: Create a pull request with a conventional title
argument-hint: "[target-branch]"
---

Create a pull request for the current branch. The target defaults to the repository's configured default branch, falling back to `main` only when it cannot be determined.

1. Confirm the current branch is not the target branch and inspect its upstream state.
2. Fetch remote state when needed, then inspect commits and the aggregate diff between the target and `HEAD`.
3. Extract a Jira key matching `[A-Z]+-[0-9]+` from the branch name when present.
4. Use a Conventional Commit-style PR title. For one commit, preserve its subject when suitable; for multiple commits, summarize the overall change.
5. Write a concise body that explains context and important implementation or validation details without adding a redundant `Summary` heading. End with `Jira: TICKET-123` when applicable.
6. Push the branch only when necessary to create the requested PR, then use `gh pr create --title ... --body ... --base ...`.

Never add co-author or AI attribution lines. Never create, update, push, or merge a PR unless the user's request authorizes that action; creating a PR never authorizes merging it.
