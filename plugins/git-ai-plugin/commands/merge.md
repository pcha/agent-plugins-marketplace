---
description: Merge or rebase a branch with conflict analysis and verification
argument-hint: "<branch> [--rebase|-r] [--no-fetch] [--no-commit]"
---

Integrate the requested branch into the current branch. Use merge by default or rebase with `--rebase`/`-r`.

1. Validate the branch or remote-tracking ref and refuse to start with an unresolved operation. If unrelated local changes could be overwritten, stop and ask how to proceed.
2. Unless `--no-fetch` is set, fetch the relevant remote ref without checking out or pulling another local branch.
3. Show the current branch, target, merge base, commits unique to each side, changed files on each side, and files changed by both sides.
4. Run `git merge <target>` or `git rebase <target>`. For merge plus `--no-commit`, use `--no-commit`; do not imply that rebase can produce a final combined state without commits.
5. If conflicts occur, inspect every conflict and the intent of both branches. Group conflicts by pattern and present one coherent resolution plan. Wait for user approval before editing conflicted files or choosing ours/theirs.
6. After an approved resolution, remove all markers, stage resolved files, continue the operation as needed, and run `git diff --check`.
7. Detect and run the project's relevant tests or checks. Report any failures without hiding them.

Do not push or force-push unless separately requested. Do not abort an existing operation or discard changes without explicit approval.
