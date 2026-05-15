# risc-skills

RISC Software internal Claude Code skills.

## Packages

| Package | Install path | Enthält |
|---------|-------------|---------|
| `risc-shared` | `shared/` | `commit`, `summarize-branch-changes`, `review` |
| `risc-dsa` | `dsa/` | alle shared Skills + DSA skill-memories |

## Installation

```bash
# Nur shared (andere Abteilungen)
npx skills add <repo-url>/shared

# DSA (Skills + skill-memories einrichten)
npx skills add <repo-url>/dsa
cp dsa/skill-memories/review.md .claude/skill-memories/review.md
```

## Skill-memories (Erweiterungen)

Skill-memories erweitern einen Base-Skill projektspezifisch ohne ihn zu forken.
Sie liegen im Projekt unter `.claude/skill-memories/<skill-name>.md`.

**Layers:**

```
shared/review.md                             ← Base (git-Befehle, allg. Checks, Output-Format)
dsa/skill-memories/review.md                ← DSA-Extension (null safety, DDD, AsciiDoc)
<projekt>/.claude/skill-memories/review.md  ← Projekt-Extension (z.B. Angular-Konventionen)
```

Für projektspezifische Erweiterungen die DSA skill-memory als Ausgangspunkt nehmen
und projektspezifische Konventionen anhängen.
