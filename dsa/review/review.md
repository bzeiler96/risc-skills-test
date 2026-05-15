---
name: review-branch
description: Review all changes between the current branch and main
---

## Fetch latest main (so we compare against the actual remote state)
!`git fetch origin main --quiet 2>/dev/null || true`

## Changed files (branch-only, via merge-base)
!`git diff origin/main...HEAD --name-only`

## Diff stats
!`git diff origin/main...HEAD --stat`

## Full diff
!`git diff origin/main...HEAD`

## Review checklist

**Before reviewing**: If the "Full diff" above was truncated or persisted to a file, use the Read tool to load the complete diff. Do not review based on stats or file lists alone — you must see the actual code changes.

Analyze the above diff and provide feedback on:

- **Correctness** — logic errors, edge cases, off-by-one mistakes
- **Null safety** — nullable values handled properly, especially in Java/Kotlin interop contexts
- **Security** — injection risks, credential exposure, OWASP top 10
- **Test coverage** — are new code paths tested? Are existing tests still valid? AsciiDoc documentation updated?
- **Documentation** — do README.md, AsciiDoc files, or CLAUDE.md need updates?

## Output format

For each finding, include:
- File path and line number
- Severity: **critical**, **warning**, or **suggestion**
- Description and recommended fix
