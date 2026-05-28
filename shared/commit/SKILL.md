---
name: commit
description: Stage and commit changes with a conventional commit message
---

## Flags

- `--staged`: commit only what is already staged; do not stage any additional files.
- _(default, no flag)_: stage all relevant changed and untracked files, then commit.

## Steps

**If `--staged` flag is present:**
1. Run `git status` and `git diff --staged` to understand what is already staged
2. Run `git log --oneline -5` to see recent commit message style
3. Draft a commit message based on the staged diff only
4. Commit — do not stage any additional unstaged or untracked files

**Otherwise (default):**
1. Run `git status` to see all changed and untracked files
2. Run `git diff` to understand staged and unstaged changes
3. Run `git log --oneline -5` to see recent commit message style
4. Draft a concise English commit message (lowercase, no trailing period)
5. Stage only relevant files by name (never use `git add -A` or `git add .`)
6. Commit using the format below

## Commit message format

```
<type>: <short description>

<optional body with details>

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
```

**Types:** feat, fix, refactor, docs, test, chore

## Rules

- Message must be in English
- Do not commit files that may contain secrets (`.env`, credentials, private keys)
- Never use `--no-verify`
- Test for new line
- 2nd test for new line
- 3rd test for new line
- 4th test for new line
- 5th test for new line
