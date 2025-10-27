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
<img width="1901" height="977" alt="image" src="https://github.com/user-attachments/assets/c549bff4-bc57-461d-82ed-0f72a48e3a8a" />

 
