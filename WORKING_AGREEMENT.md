# Team Working Agreement

## Roles
- **Lead Dev (rotates weekly):** triage issues, assign reviewers, keep `main` green.
- **Release Steward:** coordinates tag/notes if/when we cut a release.
- **QA/Testing:** champions test quality and coverage.
- **All:** self‑review PRs, respect checklist, maintain empathy in reviews.

## Communication
- Primary: Microsoft Teams / Slack channel `#team-<name>`
- Secondary: GitHub PR comments for code discussions
- Standup: async check‑in message each weekday by 10:00

## Review SLA
- First response to PRs within **24h** (workdays); escalate to Lead Dev if blocked.
- Merge queue: check twice daily (11:30, 16:30).

## Escalation Path
- If a review stalls >24h: ping reviewer → ping Lead Dev → ping instructor.

## DoR / DoD (Definition of Ready / Done)
- **Ready:** linked issue, acceptance criteria clear, test approach identified.
- **Done:** checklist satisfied, CI green, approvals met, docs/tests updated.

## Conflict Handling
- Prefer **rebase** for small divergence; **merge** when multiple contributors.
- Never blanket “ours/theirs” without reviewing; run tests after resolution.
- Record the conflict resolution commit in `/S7/README.md` with short notes.
