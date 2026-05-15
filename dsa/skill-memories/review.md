---
extends: review
description: DSA backend extension — Java/Kotlin null safety, domain-driven structure, AsciiDoc
---

Additionally check the following on top of the base `review` skill:

- **Null safety** — nullable types handled explicitly; no `!!` operator; safe-call chains (`?.`) used where appropriate; Java interop boundaries treated as nullable
- **Domain-driven structure** — business logic in domain layer, no framework leakage into domain classes, aggregates and value objects used correctly
- **Test coverage** — new code paths covered; existing tests still valid; AsciiDoc test reports (`.adoc`) updated if applicable
