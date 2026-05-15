---
name: backend-review
description: DSA backend code review — extends the shared review skill with Java/Kotlin and domain-driven specifics
---

## Fetch latest main (so we compare against the actual remote state)
!`git fetch origin main --quiet 2>/dev/null || true`

## Changed files (branch-only, via merge-base)
!`git diff origin/main...HEAD --name-only`

## Diff stats
!`git diff origin/main...HEAD --stat`

## Full diff
!`git diff origin/main...HEAD`

## Before reviewing

If the "Full diff" above was truncated or persisted to a file, use the Read tool to load the complete diff. Do not review based on stats or file lists alone — you must see the actual code changes.

## Analysis

Apply all checks from the shared `review` skill (correctness, security, documentation). Additionally check:

- **Null safety** — nullable types handled explicitly; no `!!` operator; safe-call chains (`?.`) used where appropriate; Java interop boundaries treated as nullable
- **Domain-driven structure** — business logic in domain layer, no framework leakage into domain classes, aggregates and value objects used correctly
- **Test coverage** — new code paths covered; existing tests still valid; AsciiDoc test reports (`.adoc`) updated if applicable

## Output format

Same as the shared `review` skill: file path, line number, severity (**critical** / **warning** / **suggestion**), description, recommended fix.
