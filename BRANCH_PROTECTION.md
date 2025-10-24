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

**Screenshot:**<img width="1901" height="977" alt="Screenshot 2025-10-25 003303" src="https://github.com/user-attachments/assets/8d4fd5b9-c9b7-437e-ae0d-5b5fb492e3e8" />
   


**Notes:** If you use GitLab, configure **Protected Branches** and **MR approvals** with equivalent checks.
