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

**Screenshot:**  <img width="1897" height="931" alt="Image" src="https://github.com/user-attachments/assets/589fe590-f118-4dc9-a51f-9484c415a0ff" />

**Notes:** If you use GitLab, configure **Protected Branches** and **MR approvals** with equivalent checks.
