# Branch Protection (main)

> Add a screenshot or exported settings after configuration.

**Settings used (GitHub → Settings → Branches → Branch protection rules → Add rule):**
- Branch name pattern: `main`
- ✅ Require a pull request before merging
  - Required approvals: **1** (or 2 if your team prefers)
  - Dismiss stale approvals when new commits are pushed: **On**
- ✅ Require status checks to pass before merging
  - **Required:** `CI` (the workflow in `.github/workflows/ci.yml`)
- ✅ Require conversation resolution before merging
- ✅ Require signed commits (optional)
- 🚫 Allow force pushes: **Off**
- 🚫 Allow deletions: **Off**
- (Optional) **Linear history**: On
 # Branch Protection Evidence

Screenshot showing required branch-protection settings for `main`:
- Require pull request before merging
- Require 1 approval
- Dismiss stale approvals
- Require status checks to pass

Screenshot proof below:
 <img width="1319" height="909" alt="image" src="https://github.com/user-attachments/assets/ff4ffc00-d321-4637-8d6c-98d39b930f08" />

