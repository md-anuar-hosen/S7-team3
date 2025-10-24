# Contributing Guide

Welcome! This document defines how we collaborate effectively and safely.

## Branch Naming
Use lower-case, hyphen-separated names with a short prefix:
- `feature/<short-topic>` — new code or docs
- `fix/<short-topic>` — bugfix
- `chore/<short-topic>` — tooling/config
- `docs/<short-topic>` — documentation only

Examples: `feature/login-form`, `fix/cart-total-rounding`

## Commit Style
Follow **Conventional Commits** when possible:
- `feat: add login form validation`
- `fix: correct order total rounding`
- `docs: update README with setup steps`
- `chore: enable CI workflow`
Include issue links: `Fixes #123` or `Refs #456`.

## Workflow (Model & Rationale)
We use **Mainline + short‑lived feature branches** (a.k.a. "mainline with PRs").  
**Rationale (3–5 sentences):**
- Small team and frequent merges → keeping a single, always‑green `main` with PR checks reduces integration pain.
- Short‑lived branches lower merge conflict risk and keep reviews focused (≤~300 LOC).
- CI is required on every PR; approvals by CODEOWNERS enforce shared code quality.
- Squash merges maintain a clean history while preserving PR links and context.

## Opening a Pull Request
1. Create a branch and push your changes.
2. Open a PR using the template and check every applicable box.
3. Request review from relevant CODEOWNERS (auto‑requested if paths match).
4. Ensure **CI is green** and at least **1 approval** (or 2 if configured).
5. Merge via **Squash**. Delete your branch after merge.

## Reviews SLA & Etiquette
- **First response** within **24 hours** (workdays).
- Be respectful, actionable, and specific. Prefer questions over commands.
- Authors should perform a **self‑review** before requesting others.

## Secrets & Responsible GenAI
- **Never** paste secrets or proprietary code into public AI tools.
- Allowed: drafting PR descriptions, tightening language, generating checklist ideas, brainstorming test cases.
- **Disclose in PR:** “AI assistance used: yes/no; what for.”

## Merge Policy
- Required green CI, approvals, and checklist compliance.
- Prefer **squash** merges for a readable `main` history.
