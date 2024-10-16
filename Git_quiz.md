## Multiple Choice Questions:

1. **What command is used to create a new branch in Git?**
   - a) `git checkout`
   - b) `git branch`
   - c) `git switch`
   - d) `git merge`

2. **What is the purpose of the `git checkout` command when used with branches?**
   - a) To delete a branch
   - b) To create a branch
   - c) To switch to a branch
   - d) To rename a branch

3. **Which Git command would you use to undo changes in the working directory but leave the changes in the staging area?**
   - a) `git reset --soft`
   - b) `git reset --hard`
   - c) `git checkout`
   - d) `git reset --mixed`

4. **What happens when you rebase a branch in Git?**
   - a) It merges the branch with a new commit.
   - b) It rewrites the commit history.
   - c) It deletes the branch and recreates it.
   - d) It only updates the working directory.

5. **What does a detached HEAD state mean in Git?**
   - a) You are working in a state without any commits.
   - b) You are not on any branch, and the HEAD is pointing to a specific commit.
   - c) The repository is corrupt.
   - d) HEAD is pointing to the last merge commit.

6. **How do you reapply commits that were removed during a rebase?**
   - a) `git reflog`
   - b) `git reset --hard`
   - c) `git revert`
   - d) `git stash`

7. **Which Git command is used to move changes from one branch to another without creating a merge commit?**
   - a) `git rebase`
   - b) `git merge`
   - c) `git pull`
   - d) `git cherry-pick`

8. **What does the command `git bisect` do?**
   - a) Splits a commit into two smaller commits
   - b) Reverts a merge commit
   - c) Helps find the commit that introduced a bug
   - d) Merges two branches interactively

9. **What is the difference between `git stash apply` and `git stash pop`?**
   - a) `git stash apply` creates a new stash, while `git stash pop` deletes an existing stash.
   - b) `git stash apply` re-applies stashed changes without deleting them, while `git stash pop` re-applies and removes the stash.
   - c) `git stash apply` stashes current changes, while `git stash pop` does not.
   - d) There is no difference between the two commands.

10. **Which command will show the commits that are on the current branch but not on another branch?**
   - a) `git log`
   - b) `git show-branch`
   - c) `git diff`
   - d) `git log <branch>..HEAD`

---

## Fill in the Blanks:

1. To stage all changes in a Git repository, the command used is `______`.
2. A common command to merge two branches in Git is `git ________ <branch>`.
3. In Git, `git ________ --abort` is used to stop the rebase process if conflicts occur.
4. When you want to see the commit history along with the branches, the command `git ______ --graph` can be used.
5. The three main states of a file in Git are: **modified**, **staged**, and **_______**.

---

## Short Answer Questions:

1. Explain the difference between `git reset --soft`, `git reset --mixed`, and `git reset --hard`.
2. What are the key advantages of rebasing over merging when integrating changes from one branch into another?
3. How does Git handle merge conflicts, and what tools can be used to resolve them?
4. Describe the steps to recover from a detached HEAD state and return to normal branch development.
5. What is the significance of the `.git` directory in a Git repository?

---

## True/False Questions:

1. **Merging in Git rewrites commit history.** (True/False)
2. **In Git, branches are simply pointers to commits.** (True/False)
3. **Git rebase changes the history of the repository, making it appear as though the rebased commits happened after the target branch commits.** (True/False)
4. **You can safely perform `git reset --hard` without losing any work.** (True/False)
5. **The HEAD pointer always points to the latest commit on the active branch in Git.** (True/False)

---

## Advanced Questions:

1. **Explain how `git rebase --interactive` can be used to clean up commit history. What scenarios would benefit from this?**
2. **Compare and contrast `git merge` and `git rebase` with examples of when to use each.**
3. **How would you use `git reflog` to recover a branch that was accidentally deleted or reset?**
4. **Describe the workflow to resolve conflicts during a merge, specifically focusing on the commands needed after a conflict occurs.**
5. **In a collaborative project, why might you use `git pull --rebase` instead of a normal `git pull`?**

---

## **Answer Key**:

### Multiple Choice:
1. b) `git branch`
2. c) To switch to a branch
3. d) `git reset --mixed`
4. b) It rewrites the commit history.
5. b) You are not on any branch, and the HEAD is pointing to a specific commit.
6. a) `git reflog`
7. a) `git rebase`
8. c) Helps find the commit that introduced a bug
9. b) `git stash apply` re-applies stashed changes without deleting them, while `git stash pop` re-applies and removes the stash.
10. d) `git log <branch>..HEAD`

### Fill in the Blanks:
1. `git add .`
2. `git merge`
3. `git rebase`
4. `git log`
5. `Committed`

### Short Answer:
1. **Soft, Mixed, Hard Reset**:
   - `git reset --soft`: Resets the HEAD to a previous commit but leaves the staging area and working directory intact.
   - `git reset --mixed`: Resets the HEAD and the staging area but keeps changes in the working directory.
   - `git reset --hard`: Resets the HEAD, staging area, and working directory, effectively deleting any changes.
2. **Advantages of Rebase**: Rebasing creates a linear history by applying commits on top of the target branch, avoiding unnecessary merge commits.
3. **Handling Merge Conflicts**: Git pauses the merge process if conflicts occur, allowing you to resolve them manually. Tools like `git mergetool` or conflict markers in the file can help.
4. **Recovering from Detached HEAD**: To recover, create a new branch using `git checkout -b <branch_name>` and continue working on that branch.
5. **Significance of .git Directory**: The `.git` directory stores all the metadata, including the history of commits, branches, and configuration settings for the repository.

### True/False:
1. False
2. True
3. True
4. False
5. True
"""
