# /commit

Erstelle einen Git-Commit nach RISC-Konventionen.

## Verhalten

1. Führe `git diff --staged` aus um die gestageten Änderungen zu sehen
2. Falls nichts gestaget ist, führe `git status` aus und frage den User was committet werden soll
3. Schreibe eine Commit-Message nach dem Schema: `<type>(<scope>): <beschreibung>`
4. Erstelle den Commit — kein `--no-verify`

## Commit-Types

- `feat` — neue Funktionalität
- `fix` — Bugfix
- `refactor` — Umstrukturierung ohne Verhaltensänderung
- `docs` — Dokumentation
- `test` — Tests
- `chore` — Build, Dependencies, CI

## Regeln

- Beschreibung auf Deutsch, max. 72 Zeichen
- Kein Punkt am Ende der Subject-Line
- Breaking Changes im Footer mit `BREAKING CHANGE:` kennzeichnen
