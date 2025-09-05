# IXI Lab Quick Reference

> **The most frequently used commands and rules in our lab**

## Branch Flow Diagram

```
main (stable) ← develop (integration) ← feature/your-task
     ↑                    ↑                    ↑
  (Owners only)    (Team Leaders)      (All Members)
```

## Essential Commands

### Daily Workflow
```bash
# Get latest changes
git checkout develop
git pull origin develop

# Create new feature branch
git checkout -b feature/your-task-name

# Save your work
git add .
git commit -m "feat: your descriptive message"
git push origin feature/your-task-name
```

### Branch Management
```bash
# List all branches
git branch

# Switch between branches
git checkout branch-name

# Delete old branch (after PR is merged)
git checkout develop
git branch -d feature/old-branch
```

## Branch Naming Convention

| Type | Format | Example |
|------|--------|---------|
| **Feature** | `feature/description` | `feature/power-spectrum-analysis` |
| **Bug Fix** | `bugfix/description` | `bugfix/fix-data-loader-crash` |
| **Experiment** | `experiment/description` | `experiment/try-transformer-model` |

## Commit Message Format

```
type: brief description

feat: Add power spectrum analysis function
fix: Resolve memory leak in data loader
docs: Update API documentation
refactor: Simplify matrix multiplication logic
```

**Types:** `feat`, `fix`, `docs`, `refactor`, `test`, `style`

## Critical Rules

> **NEVER push large files** (>50MB). Use `.gitignore` for data files.

> **Always create branches** from `develop`, never from `main`.

> **Pull before you push** to avoid conflicts.

> **Delete old branches** after PRs are merged.

## Project Structure Rules

- **`/src/`** - Version controlled (your code)
- **`/data/`** - Ignored by Git (raw data)
- **`/results/`** - Ignored by Git (outputs)
- **`/manuscript/`** - Version controlled (papers)

## Pull Request Process

1. **Create PR** from `feature/branch` → `develop`
2. **Request review** from Team Leader
3. **Address feedback** if needed
4. **Team Leader merges** to `develop`
5. **Delete branch** after merge

## Emergency Commands

### Undo last commit (before pushing)
```bash
git reset --soft HEAD~1
```

### Check file sizes before committing
```bash
find . -size +50M -type f
```

### See what files are staged
```bash
git status
```

## Role Permissions

| Role | Can Merge to | Can Create Projects | Can Manage Teams |
|------|-------------|-------------------|------------------|
| **Member** | No | No | No |
| **Team Leader** | `develop` | No | Yes (their project) |
| **Owner** | `main` & `develop` | Yes | Yes (all projects) |

## Essential Links

- [GitHub Docs: About Branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches)
- [GitHub Docs: About Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
- [GitHub Docs: Ignoring Files](https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files)

---

> **Remember:** When in doubt, ask your Team Leader or check the detailed guides in this documentation hub!
