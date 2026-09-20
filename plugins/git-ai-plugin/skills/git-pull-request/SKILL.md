---
name: git-pull-request
description: Create a GitHub pull request when the user explicitly asks to open or create a PR from the current branch. Do not use for PR review, issue creation, or merging an existing PR.
---

# Git Pull Request

Determine the target from the request or the repository's default branch. Verify the current branch, upstream state, commits, and aggregate diff against the target. Fetch when current remote state is needed.

Use a Conventional Commit-style title. Preserve a suitable single-commit subject; otherwise summarize all branch commits. The body should explain context and important implementation or validation details without a redundant `Summary` heading. Add `Jira: KEY-123` at the end when the branch contains a Jira key matching `[A-Z]+-[0-9]+`. Never add co-author or AI attribution lines.

Push the branch only as needed for the requested PR, then create it with `gh pr create`. Report the resulting URL. Never merge, enable auto-merge, or change an existing PR unless separately requested.
