---
name: summarize-branch-changes
description: Generates a short, clear, and developer-friendly summary of the main changes in a branch compared to its source branch. Suitable for merge requests, pull requests, or Jira tickets.
---

## Purpose

This skill creates a **concise, high-signal summary** of what changed in a branch relative to its source (e.g., `main`, `develop`).  
The output is optimized for quick understanding by other developers and stakeholders.

It should:
- Describe the issue or feature
- Highlight **what changed and why**
- Avoid low-level noise (e.g., formatting-only changes unless relevant)
- Be easily pasteable into merge requests or Jira tickets

---

## Input

Provide one or more of the following:

- Git diff (`git diff <source>...<branch>`)
- Commit messages (`git log`)
- Pull/Merge request description
- File change list (`git diff --name-status`)
- Relevant context (feature, bugfix, refactor, etc.)

---

## Output Format

The summary MUST follow this structure:

### 📌 Title
A single concise line (max 72 characters) suitable as a merge request or PR title. Format: `<type>: <short description>` using types `feat`, `fix`, `refactor`, `chore`, `docs`. No trailing period.

### 🧾 Summary of Changes
A short paragraph (2–4 sentences) describing the overall intent and impact.

### 🔑 Key Changes
- Bullet points of the most important changes
- Focus on functionality, behavior, architecture, or interfaces
- Group related changes when appropriate

### ⚠️ Notes (optional)
- Breaking changes
- Migration steps
- Known limitations
- Important side effects

---

## Style Guidelines

- Be **concise but informative**
- Prefer **developer-centric language**
- Avoid listing every file unless necessary
- Do NOT repeat commit messages verbatim — synthesize them
- Emphasize **intent over implementation details**
- Use consistent terminology

---

## Examples

### Example Input (simplified)
- Added new API endpoint for user creation
- Refactored authentication middleware
- Fixed bug in token refresh logic
- Updated unit tests

### Example Output

### 📌 Title
feat: add user creation endpoint and fix token refresh

### 🧾 Summary of Changes
Introduces a new user creation endpoint and improves authentication handling. Existing token refresh issues have been resolved, and the authentication layer was refactored for better maintainability.

### 🔑 Key Changes
- Added `/users` API endpoint for creating new users
- Refactored authentication middleware to improve structure and reuse
- Fixed token refresh bug causing premature session expiration
- Updated and extended unit tests for authentication flows

### ⚠️ Notes
- Authentication changes may affect existing integrations relying on old middleware behavior

---

## Instructions

When generating the summary:
1. Identify the **main purpose** of the branch (feature, fix, refactor, etc.)
2. Extract **high-impact changes**
3. Remove redundant or low-value details
4. Group related changes into meaningful bullets
5. Add notes only if relevant

---

## Anti-Patterns

Avoid:
- Dumping raw commit logs
- Overly long explanations
- File-by-file change listings without context
- Vague summaries like "various improvements"

---

## Success Criteria

A good summary allows a developer to:
- Understand the change in **< 30 seconds**
- Decide if deeper review is needed
- Identify potential risks or impacts quickly
