# risc-skills

RISC Software internal Claude Code skills.

## Packages

| Package | Path | Contains |
|---------|------|----------|
| `risc-shared` | `shared/` | `commit`, `summarize-branch-changes`, `review` |
| `risc-dsa` | `dsa/` | all shared skills + DSA skill-memories |

## Installation

```bash
# Shared only (other departments)
npx skills add <repo-url>/shared

# DSA (skills + skill-memories)
npx skills add <repo-url>/dsa
cp dsa/skill-memories/review.md .claude/skill-memories/review.md
```

## Skill-memories (extensions)

Skill-memories extend a base skill without forking it.
They live in the project under `.claude/skill-memories/<skill-name>.md`.

**Three layers:**

```
shared/review.md                             ← Base (git commands, general checks, output format)
dsa/skill-memories/review.md                ← DSA extension (null safety, DDD, AsciiDoc)
<project>/.claude/skill-memories/review.md  ← Project extension (e.g. Angular conventions)
```

For project-specific extensions, use the DSA skill-memory as a starting point and append project-specific conventions.
