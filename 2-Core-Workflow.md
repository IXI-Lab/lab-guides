# Core Workflow - Daily Research Cycle

> **The essential daily workflow for all lab members**

This guide covers the fundamental cycle you'll use every day: getting a project, making changes, and contributing them back to the team.

## The Complete Cycle

Here's the 5-step process you'll follow for every task:

1. **Clone** - Get the project on your computer
2. **Branch** - Create your own workspace
3. **Commit** - Save your progress
4. **Push** - Share your work
5. **Pull Request** - Request review and merge

## Step 1: Cloning a Project

"Cloning" downloads a project from GitHub to your computer. You only do this **once per project**.

### Method 1: Using VS Code (Recommended)

1. **Open VS Code**
2. **Open Command Palette**: `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac)
3. **Type**: `Git: Clone`
4. **Paste the repository URL** (your Team Leader will provide this)
5. **Choose a location** on your computer to save the project
6. **Click "Open"** when the clone completes

### Method 2: Using Terminal

1. **Open a terminal** in VS Code
2. **Navigate** to where you want to save the project:
   ```bash
   cd Documents/GitHub_Projects/
   ```
3. **Clone the repository**:
   ```bash
   git clone https://github.com/IXI-Lab/your-project-name.git
   ```
4. **Open the project** in VS Code: `File` → `Open Folder`

## Step 2: Creating Your Branch (Team Leader Will Do It)

Before writing any code, create your own **branch** - a safe workspace where you can experiment without affecting others.

### Get the Latest Changes

Always start from the most current version:

```bash
git checkout develop
git pull origin develop
```

### Create Your Feature Branch

```bash
git checkout -b feature/your-task-description
```

**Branch naming examples:**
- `feature/power-spectrum-analysis`
- `feature/add-data-validation`
- `bugfix/fix-memory-leak`

> **Critical Rule:** Always create branches from `develop`, never from `main`!

## Step 3: Saving Your Work (Add & Commit)

As you work, you need to save snapshots of your progress. This is a two-step process:

### Step 3a: Stage Your Changes

**Using VS Code (Recommended):**
1. Click the **Source Control icon** in the left sidebar
2. You'll see modified files under "Changes"
3. Click the **+ icon** next to files you want to save
4. Or click the **+ icon** next to "Changes" to stage all files

**Using Terminal:**
```bash
# Stage a specific file
git add src/analysis/new_script.py

# Stage all modified files
git add .
```

### Step 3b: Commit Your Changes

**Using VS Code:**
1. With files staged, type your commit message in the text box
2. Follow our format: `feat: Add power spectrum analysis function`
3. Click the **checkmark icon** to commit

**Using Terminal:**
```bash
git commit -m "feat: Add power spectrum analysis function"
```

### Commit Message Format

```
type: brief description

feat: Add new functionality
fix: Fix a bug
docs: Update documentation
refactor: Improve code structure
```

**Types:** `feat`, `fix`, `docs`, `refactor`, `test`, `style`

## Step 4: Pushing to GitHub

Your commits are saved locally until you **push** them to GitHub.

### First Push (New Branch)

**Using VS Code:**
- Click **"Publish Branch"** button in the Source Control panel

**Using Terminal:**
```bash
git push -u origin feature/your-branch-name
```

### Subsequent Pushes

**Using VS Code:**
- Click **"Sync Changes"** button (circular arrow icon)

**Using Terminal:**
```bash
git push
```

## Step 5: Creating a Pull Request

After pushing, you'll see a prompt on GitHub to create a **Pull Request (PR)**.

1. **Click "Compare & pull request"** on GitHub
2. **Set the base branch** to `develop` (should be default)
3. **Write a clear title** and description
4. **Request review** from your Team Leader
5. **Wait for review** and address any feedback
6. **Team Leader merges** your PR to `develop`

## Step 6: Cleanup

After your PR is merged:

1. **Delete the remote branch** (GitHub usually provides a button)
2. **Switch back to develop**:
   ```bash
   git checkout develop
   git pull origin develop
   ```
3. **Delete your local branch**:
   ```bash
   git branch -d feature/your-branch-name
   ```

## Daily Workflow Example

Here's a complete example for adding a new analysis function:

```bash
# 1. Get latest changes
git checkout develop
git pull origin develop

# 2. Create your branch
git checkout -b feature/add-correlation-analysis

# 3. Work on your code...
# (Edit files in VS Code)

# 4. Save your work
git add .
git commit -m "feat: Add correlation analysis function"

# 5. Push to GitHub
git push -u origin feature/add-correlation-analysis

# 6. Create PR on GitHub (via web interface)

# 7. After PR is merged, cleanup
git checkout develop
git pull origin develop
git branch -d feature/add-correlation-analysis
```

## Common Mistakes to Avoid

> **Don't work directly on `main` or `develop`** - always create a feature branch

> **Don't commit large files** (>50MB) - they'll be rejected

> **Don't forget to pull** before starting new work

> **Don't leave old branches** - delete them after merging

## When Things Go Wrong

### "Your branch is behind"
```bash
git checkout develop
git pull origin develop
git checkout your-branch
git merge develop
```

### "Permission denied"
- Make sure you're invited to the repository
- Check your GitHub authentication in VS Code

### "Large file detected"
- See [Emergency Procedures](4-Emergency-Procedures.md) for how to fix this

## What's Next?

- **Complex projects?** → [Branching Workflows](3-Branching-Workflows.md)
- **Need a quick reminder?** → [Quick Reference](QUICK_REFERENCE.md)
- **Emergency situation?** → [Emergency Procedures](4-Emergency-Procedures.md)

---

> **Pro Tip:** Practice this workflow with small changes first. Once you're comfortable, you'll be able to work efficiently on any project in the lab!
