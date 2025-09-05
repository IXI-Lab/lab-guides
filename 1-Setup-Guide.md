# Setup Guide - Getting Your Computer Ready

> **One-time setup for new lab members**

This guide will walk you through setting up your computer to work with our GitHub-based research workflow. You only need to do this once!

## Prerequisites

- A computer with internet access
- A GitHub account (if you don't have one, create it at [github.com](https://github.com))
- Administrator access to install software

## Step 1: Install Visual Studio Code

VS Code is our recommended code editor with excellent built-in Git support.

1. **Download VS Code** from [code.visualstudio.com](https://code.visualstudio.com/)
2. **Install** following the default settings
3. **Launch VS Code** to verify it works

> **Why VS Code?** It has excellent Git integration, supports all programming languages we use, and provides a consistent experience across different operating systems.

## Step 2: Install Git

Git is the version control system that powers GitHub.

1. **Download Git** from [git-scm.com/downloads](https://git-scm.com/downloads)
2. **Install** accepting all default settings
3. **Verify installation** by opening a terminal and typing:
   ```bash
   git --version
   ```
   You should see a version number (e.g., `git version 2.39.0`)

## Step 3: Configure Git with Your Identity

You must tell Git who you are. This name and email will be attached to every **commit** you make.

1. **Open a terminal** in VS Code:
   - Click **Terminal** → **New Terminal** in the menu bar
   - Or use the keyboard shortcut: `Ctrl+Shift+` (Windows/Linux) or `Cmd+Shift+` (Mac)

2. **Set your name and email**:
   ```bash
   git config --global user.name "Your Full Name"
   git config --global user.email "your.email@github.com"
   ```

> **Important:** Use the same email address that you use for your GitHub account!

3. **Verify your configuration**:
   ```bash
   git config --global --list
   ```
   You should see your name and email in the output.

## Step 4: Connect VS Code to GitHub

This final step allows VS Code to securely communicate with your GitHub account.

1. **In VS Code**, click the **accounts icon** in the bottom-left corner
2. **Sign in with GitHub** and follow the authentication prompts
3. **Grant permissions** when prompted by your browser
4. **Verify connection** - you should see your GitHub username in the bottom-left corner

## Step 5: Test Your Setup

Let's verify everything works by cloning a test repository:

1. **Open VS Code**
2. **Open Command Palette**: `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac)
3. **Type**: `Git: Clone`
4. **Enter this test URL**: `https://github.com/octocat/Hello-World.git`
5. **Choose a location** to save the test repository
6. **Click "Open"** when prompted

If this works without errors, your setup is complete!

## Cleanup

You can now delete the test repository:
- Close VS Code
- Delete the `Hello-World` folder from your computer

## Troubleshooting

### Git command not found
- **Windows**: Restart your computer after installing Git
- **Mac/Linux**: Make sure Git is in your PATH

### VS Code can't connect to GitHub
- Check your internet connection
- Try signing out and back in to GitHub in VS Code
- Make sure you're using the correct GitHub account

### Permission denied errors
- Make sure you're using the correct email address
- Verify your GitHub account is active

## What's Next?

Now that your computer is set up, you're ready to:

1. **Learn the daily workflow** → [Core Workflow Guide](2-Core-Workflow.md)
2. **Get a quick reference** → [Quick Reference](QUICK_REFERENCE.md)
3. **Join a project** - Ask your Team Leader to invite you to a repository

## Additional Resources

- [VS Code Documentation](https://code.visualstudio.com/docs)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Documentation](https://docs.github.com)

---

> **Pro Tip:** Bookmark the [Quick Reference](QUICK_REFERENCE.md) page - you'll use it frequently once you start working on projects!
