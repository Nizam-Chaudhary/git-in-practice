# Git Commands Cheat Sheet

A detailed reference guide for common Git operations.

## 1. Setup & Configuration

| Command | Description |
| :--- | :--- |
| `git init` | Initialize a new local Git repository. |
| `git clone <url>` | Clone a repository from a remote server. |
| `git config --global user.name "Name"` | Set your name for commits. |
| `git config --global user.email "email@example.com"` | Set your email for commits. |
| `git config --list` | List all local configurations. |

## 2. Basic Snapshotting

| Command | Description |
| :--- | :--- |
| `git status` | Show the status of changes (untracked, modified, staged). |
| `git add <file>` | Add a specific file to the staging area. |
| `git add .` | Add all changes (new, modified, deleted) to staging. |
| `git commit -m "message"` | Commit staged changes with a descriptive message. |
| `git commit -am "message"` | Stage all tracked files and commit in one step. |
| `git commit --amend` | Modify the last commit (change message or add forgotten files). |

## 3. Branching & Merging

| Command | Description |
| :--- | :--- |
| `git branch` | List all local branches. |
| `git branch <name>` | Create a new branch. |
| `git checkout <branch>` | Switch to a specific branch. |
| `git switch <branch>` | Modern way to switch branches. |
| `git checkout -b <name>` | Create and switch to a new branch. |
| `git merge <branch>` | Merge the specified branch into the current one. |
| `git branch -d <name>` | Delete a local branch. |
| `git rebase <branch>` | Reapply commits on top of another base tip. |

## 4. Sharing & Updating (Remotes)

| Command | Description |
| :--- | :--- |
| `git remote add <name> <url>` | Connect local repo to a remote server. |
| `git remote -v` | List all connected remotes. |
| `git push <remote> <branch>` | Upload local commits to the remote. |
| `git pull <remote> <branch>` | Fetch and merge changes from the remote. |
| `git fetch <remote>` | Download changes from remote without merging. |

## 5. Inspection & Comparison

| Command | Description |
| :--- | :--- |
| `git log` | Show commit history. |
| `git log --oneline --graph --all` | Visual representation of history. |
| `git diff` | Show changes between working directory and staging. |
| `git diff --staged` | Show changes between staging and last commit. |
| `git diff <branch1> <branch2>` | Compare differences between two branches. |
| `git show <commit>` | Show details of a specific commit. |

## 6. Undoing Changes

| Command | Description |
| :--- | :--- |
| `git restore <file>` | Discard changes in the working directory (revert to last commit). |
| `git restore --staged <file>` | Unstage a file but keep the changes in working directory. |
| `git reset --soft HEAD~1` | Undo last commit, keeping changes staged. |
| `git reset --hard HEAD~1` | Undo last commit and **discard all changes**. (Dangerous!) |
| `git revert <commit>` | Create a new commit that undoes the changes of a previous one. |

## 7. Stashing & Advanced Tools

| Command | Description |
| :--- | :--- |
| `git stash` | Temporarily save uncommitted changes and clean work dir. |
| `git stash pop` | Restore the most recently stashed changes and remove from stash list. |
| `git stash list` | List all stashed changes. |
| `git worktree add <path> <branch>` | Check out a branch into a separate directory. |
| `git clean -fd` | Remove untracked files and directories. |

## 8. Git Log Formatting Tips

- `git log --author="Name"`: Filter by author.
- `git log --since=2.weeks`: Filter by date.
- `git log -S "string"`: Find commits that introduced/removed a specific string.
