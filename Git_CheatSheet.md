
# Git Cheat Sheet

## Table of Contents:
1. [Introduction to Git](#introduction-to-git)
2. [Git Configuration](#git-configuration)
3. [Git Basics](#git-basics)
   - [Repositories](#repositories)
   - [Cloning a Repository](#cloning-a-repository)
   - [Staging and Committing Changes](#staging-and-committing-changes)
   - [Pushing and Pulling Changes](#pushing-and-pulling-changes)
4. [Branches in Git](#branches-in-git)
   - [Creating and Switching Branches](#creating-and-switching-branches)
   - [Merging Branches](#merging-branches)
   - [Rebasing](#rebasing)
   - [Cherry-picking Commits](#cherry-picking-commits)
5. [Git Reset, Revert, and Restore](#git-reset-revert-and-restore)
6. [Git Logs and History](#git-logs-and-history)
7. [Undoing Changes](#undoing-changes)
8. [Working with Remote Repositories](#working-with-remote-repositories)
9. [Git Tags](#git-tags)
10. [Advanced Git Topics](#advanced-git-topics)
    - [Git Stash](#git-stash)
    - [Git Bisect](#git-bisect)
    - [Git Hooks](#git-hooks)
    - [Git Reflog](#git-reflog)

---

## Introduction to Git
**Git** is a distributed version control system used to track changes in source code during software development. It allows multiple developers to work together on projects without overriding each other's changes.

---

## Git Configuration
Before starting to use Git, it is essential to configure your user details:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

- To view all configurations:
  ```bash
  git config --list
  ```

---

## Git Basics

### Repositories
A **repository** (or "repo") is a directory that contains your project files and a special `.git` folder, which tracks all changes made to files in the repo.

- To initialize a repository:
  ```bash
  git init
  ```

### Cloning a Repository
- To clone an existing repository:
  ```bash
  git clone <repository-url>
  ```

### Staging and Committing Changes
1. **Stage files**:
   ```bash
   git add <file>
   git add .
   ```
   This command stages files, making them ready for commit.

2. **Commit changes**:
   ```bash
   git commit -m "Commit message"
   ```
   This command records the changes to the repository.

### Pushing and Pulling Changes
- **Push changes** to the remote repository:
  ```bash
  git push origin <branch>
  ```

- **Pull changes** from the remote repository:
  ```bash
  git pull origin <branch>
  ```

---

## Branches in Git
**Branches** allow you to work on different versions of your project simultaneously. The `main` branch is the default branch where final code is stored.

### Creating and Switching Branches
- To create a new branch:
  ```bash
  git branch <branch-name>
  ```

- To switch to a branch:
  ```bash
  git checkout <branch-name>
  ```
  or
  ```bash
  git switch <branch-name>
  ```

### Merging Branches
- To merge changes from one branch into another:
  ```bash
  git checkout <target-branch>
  git merge <source-branch>
  ```

### Rebasing
- Rebasing allows you to integrate changes from one branch into another by rewriting the commit history:
  ```bash
  git rebase <branch>
  ```

### Cherry-picking Commits
- To apply a specific commit from one branch to another:
  ```bash
  git cherry-pick <commit-hash>
  ```

---

## Git Reset, Revert, and Restore
- **git reset**: Undo commits by moving the HEAD and optionally modifying the working directory.
  ```bash
  git reset --soft <commit-hash>  # Keeps changes in staging area
  git reset --mixed <commit-hash>  # Default, keeps changes in working directory
  git reset --hard <commit-hash>  # Discards all changes
  ```

- **git revert**: Undo a commit by creating a new commit that undoes the changes.
  ```bash
  git revert <commit-hash>
  ```

- **git restore**: Restore changes in the working directory or discard changes in a specific file.
  ```bash
  git restore <file>
  git restore --staged <file>  # Unstage a file
  ```

---

## Git Logs and History
- To view the commit history:
  ```bash
  git log
  ```

- To view the log with a graphical representation of branches:
  ```bash
  git log --graph --oneline --all
  ```

- To view changes made to files:
  ```bash
  git diff
  ```

---

## Undoing Changes
- **Unstage a file**:
  ```bash
  git reset HEAD <file>
  ```

- **Discard changes in the working directory**:
  ```bash
  git checkout -- <file>
  ```

---

## Working with Remote Repositories
- To view remote repositories:
  ```bash
  git remote -v
  ```

- To add a remote repository:
  ```bash
  git remote add origin <repository-url>
  ```

- To fetch changes from the remote repository:
  ```bash
  git fetch origin
  ```

---

## Git Tags
**Tags** are used to mark specific points in the commit history, often used for releases.

- To create a tag:
  ```bash
  git tag <tag-name>
  ```

- To push tags to the remote repository:
  ```bash
  git push origin <tag-name>
  ```

---

## Advanced Git Topics

### Git Stash
The **stash** command temporarily saves changes without committing them.
- Save changes to the stash:
  ```bash
  git stash
  ```

- Apply stashed changes:
  ```bash
  git stash apply
  ```

- Pop the stash (apply and remove):
  ```bash
  git stash pop
  ```

### Git Bisect
The **bisect** command helps find which commit introduced a bug by performing a binary search.
- Start bisecting:
  ```bash
  git bisect start
  ```

### Git Hooks
**Git hooks** are scripts that run automatically before or after Git events (e.g., commits or merges).

- Common hook examples:
  - `pre-commit`: Runs before a commit is made.
  - `post-merge`: Runs after a merge.

### Git Reflog
**Reflog** tracks updates to the tip of branches, even those that aren't recorded in regular logs.

- To view the reflog:
  ```bash
  git reflog
  ```

- To recover a branch or commit:
  ```bash
  git checkout <reflog-hash>
  ```

---

## Conclusion
Git is a powerful tool that enables developers to manage and track changes in their codebases. By understanding branches, commits, rebasing, and other key concepts, you can collaborate effectively with others and maintain a clean project history. Mastering advanced features like `git stash`, `git bisect`, and `git hooks` can further improve your productivity and help you manage large-scale projects more efficiently.
