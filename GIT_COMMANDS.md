# Basic Git Commands Guide

This guide explains essential Git commands and how to use them. Git is a distributed version control system that helps you track changes in your code and collaborate with others.

## Table of Contents
- [git init](#git-init)
- [git clone](#git-clone)
- [git status](#git-status)
- [git add](#git-add)
- [git commit](#git-commit)
- [git push](#git-push)
- [git pull](#git-pull)

---

## git init

**Purpose:** Initialize a new Git repository in your current directory.

**Usage:**
```bash
git init
```

**Example:**
```bash
# Create a new directory for your project
mkdir my-project
cd my-project

# Initialize Git repository
git init

# Output: Initialized empty Git repository in /path/to/my-project/.git/
```

**What happens:** Creates a hidden `.git` directory that contains all the necessary metadata and version history for your repository.

---

## git clone

**Purpose:** Create a local copy of a remote repository.

**Usage:**
```bash
git clone <repository-url>
```

**Examples:**
```bash
# Clone a repository using HTTPS
git clone https://github.com/username/repository.git

# Clone a repository using SSH
git clone git@github.com:username/repository.git

# Clone into a specific directory
git clone https://github.com/username/repository.git my-folder

# Clone a specific branch
git clone -b branch-name https://github.com/username/repository.git
```

**What happens:** Downloads the entire repository including all files, branches, and commit history to your local machine.

---

## git status

**Purpose:** Display the current state of your working directory and staging area.

**Usage:**
```bash
git status
```

**Example:**
```bash
# Check repository status
git status

# Example output:
# On branch main
# Your branch is up to date with 'origin/main'.
#
# Changes not staged for commit:
#   modified:   README.md
#
# Untracked files:
#   new-file.txt
```

**What it shows:**
- Current branch
- Files that have been modified
- Files that are staged for commit
- Untracked files (new files not yet added to Git)
- Whether your branch is ahead/behind the remote branch

---

## git add

**Purpose:** Add file changes to the staging area, preparing them for commit.

**Usage:**
```bash
git add <file-name>
```

**Examples:**
```bash
# Add a specific file
git add index.html

# Add multiple files
git add file1.js file2.js file3.css

# Add all files in current directory
git add .

# Add all files in the repository
git add -A

# Add all files with a specific extension
git add *.js

# Add all files in a specific directory
git add src/

# Interactively add changes
git add -p
```

**What happens:** Moves changes from your working directory to the staging area, marking them to be included in the next commit.

---

## git commit

**Purpose:** Save your staged changes to the local repository with a descriptive message.

**Usage:**
```bash
git commit -m "commit message"
```

**Examples:**
```bash
# Commit with a message
git commit -m "Add user authentication feature"

# Commit with a detailed message
git commit -m "Add user authentication" -m "Implemented login and registration functionality with JWT tokens"

# Add all tracked modified files and commit in one step
git commit -am "Fix typo in documentation"

# Open default text editor for longer commit message
git commit

# Amend the last commit (add more changes or update message)
git commit --amend -m "Updated commit message"
```

**Best Practices for Commit Messages:**
- Use present tense ("Add feature" not "Added feature")
- Keep the first line under 50 characters
- Be descriptive but concise
- Use the imperative mood ("Fix bug" not "Fixes bug")

---

## git push

**Purpose:** Upload your local repository commits to a remote repository.

**Usage:**
```bash
git push <remote> <branch>
```

**Examples:**
```bash
# Push to the default remote (origin) and current branch
git push

# Push to origin's main branch
git push origin main

# Push to origin's specific branch
git push origin feature-branch

# Push and set upstream tracking
git push -u origin main

# Push all branches
git push --all origin

# Push tags
git push --tags

# Force push (use with caution!)
git push --force origin main
```

**What happens:** Sends your committed changes to the remote repository, making them available to other team members.

**Note:** You need to have write access to the remote repository to push changes.

---

## git pull

**Purpose:** Download and integrate changes from a remote repository into your current branch.

**Usage:**
```bash
git pull <remote> <branch>
```

**Examples:**
```bash
# Pull from the default remote and current branch
git pull

# Pull from origin's main branch
git pull origin main

# Pull from a specific remote and branch
git pull upstream develop

# Pull with rebase instead of merge
git pull --rebase origin main

# Pull but don't commit the merge
git pull --no-commit origin main
```

**What happens:** Combines two operations:
1. `git fetch` - Downloads changes from the remote repository
2. `git merge` - Integrates those changes into your current branch

**Note:** Before pulling, make sure your working directory is clean (commit or stash your changes) to avoid conflicts.

---

## Common Workflow Example

Here's a typical workflow combining these commands:

```bash
# 1. Clone a repository
git clone https://github.com/username/project.git
cd project

# 2. Check current status
git status

# 3. Make changes to files (edit, create, delete)
# ... make your changes ...

# 4. Check what changed
git status

# 5. Stage your changes
git add .

# 6. Commit your changes
git commit -m "Add new feature"

# 7. Pull latest changes from remote (to avoid conflicts)
git pull origin main

# 8. Push your changes to remote
git push origin main
```

## Additional Tips

- **Always check status:** Use `git status` frequently to understand the current state
- **Commit often:** Make small, focused commits rather than large ones
- **Pull before push:** Always pull the latest changes before pushing to avoid conflicts
- **Write clear messages:** Good commit messages help you and your team understand the history
- **Use branches:** Create feature branches for new work to keep main branch stable

---

## Need Help?

For more information about any Git command, use:
```bash
git help <command>
# Example: git help commit
```

Or visit the [official Git documentation](https://git-scm.com/doc).
