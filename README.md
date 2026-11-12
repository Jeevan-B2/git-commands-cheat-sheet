# 🚀 The Ultimate Git Commands Cheat Sheet

A comprehensive, beginner-to-advanced reference guide for the most essential Git commands. 

> **📌 Note:** Text in `<angle_brackets>` should be replaced with your specific values (e.g., `<branch-name>`, `<file-name>`).

---

## 📖 Table of Contents
1. [Setup & Configuration](#1-setup--configuration)
2. [Getting & Creating Projects](#2-getting--creating-projects)
3. [Basic Snapshotting (Staging & Committing)](#3-basic-snapshotting)
4. [Branching & Merging](#4-branching--merging)
5. [Remote Repositories (GitHub/GitLab)](#5-remote-repositories)
6. [Undoing Changes (Fixing Mistakes)](#6-undoing-changes)
7. [Stashing (Saving Work Temporarily)](#7-stashing)
8. [Viewing History & Logs](#8-viewing-history--logs)
9. [Advanced Operations (Rebase & Cherry-pick)](#9-advanced-operations)

---

## 1. ⚙️ Setup & Configuration
Set up your identity and preferences. This is the first thing you should do after installing Git.

| Command | Description |
| :--- | :--- |
| `git config --global user.name "Your Name"` | Sets your name for commit history. |
| `git config --global user.email "email@example.com"` | Sets your email for commit history. |
| `git config --global core.editor "code --wait"` | Sets VS Code as your default text editor for Git. |
| `git config --list` | Lists all your current Git configuration settings. |

---

## 2. 📁 Getting & Creating Projects
How to start a new project or grab an existing one.

| Command | Description |
| :--- | :--- |
| `git init` | Initializes a new local Git repository in the current folder. |
| `git clone <url>` | Downloads a remote repository to your local machine. |
| `git clone <url> --depth 1` | Clones only the latest commit (faster, saves space). |

---

## 3. 📸 Basic Snapshotting (Staging & Committing)
The core workflow of Git: Modify -> Stage -> Commit.

| Command | Description |
| :--- | :--- |
| `git status` | Shows the state of your working directory and staging area. |
| `git add <file>` | Stages a specific file for the next commit. |
| `git add .` | Stages **all** changed and new files in the current directory. |
| `git commit -m "Your message"` | Records the staged changes with a descriptive message. |
| `git commit -am "Message"` | Stages and commits **already tracked** files in one step. |
| `git commit --amend` | Modifies the very last commit (adds files or changes the message). |

---

## 4. 🌿 Branching & Merging
Isolate your work. Never work directly on the `main` branch.

| Command | Description |
| :--- | :--- |
| `git branch` | Lists all local branches. |
| `git branch -a` | Lists all local AND remote branches. |
| `git branch <branch-name>` | Creates a new branch. |
| `git checkout <branch-name>` | Switches to an existing branch. |
| `git checkout -b <branch-name>` | Creates **and** switches to a new branch immediately. |
| `git switch <branch-name>` | (Modern alternative) Switches branches. |
| `git merge <branch-name>` | Merges the specified branch into your current branch. |
| `git branch -d <branch-name>` | Deletes a branch (only if fully merged). |
| `git branch -D <branch-name>` | **Force deletes** a branch (even if unmerged). |

---

## 5. 🌐 Remote Repositories
Working with GitHub, GitLab, or Bitbucket.

| Command | Description |
| :--- | :--- |
| `git remote -v` | Lists the remote URLs associated with your repo. |
| `git remote add origin <url>` | Links your local repo to a remote server. |
| `git fetch` | Downloads new data from a remote repo (but doesn't merge it). |
| `git pull` | Fetches remote changes **and** merges them into your local branch. |
| `git push origin <branch-name>` | Uploads your local commits to the remote branch. |
| `git push -u origin <branch-name>` | Pushes and sets the upstream (tracks the remote branch). |

> [!WARNING]
> **Danger Zone:** `git push --force` overwrites remote history. Never use this on the `main` branch of a shared repository unless absolutely necessary.

---

## 6. ⏪ Undoing Changes (Fixing Mistakes)
The most important section to master!

| Command | Description |
| :--- | :--- |
| `git restore <file>` | Discards changes in your working directory (reverts to last commit). |
| `git restore --staged <file>` | Unstages a file (removes it from `git add`). |
| `git reset --soft HEAD~1` | Undoes the last commit, but keeps your changes staged. |
| `git reset --mixed HEAD~1` | Undoes the last commit, keeps changes in working directory (unstaged). |
| `git reset --hard HEAD~1` | ⚠️ **Destructive:** Undoes the last commit and **deletes** all changes. |
| `git revert <commit-hash>` | Creates a *new* commit that undoes the changes of a specific previous commit (safe for shared branches). |
| `git clean -fd` | Removes untracked files and directories. |

---

## 7. 📦 Stashing (Saving Work Temporarily)
Use when you need to switch branches but don't want to commit half-finished work.

| Command | Description |
| :--- | :--- |
| `git stash` | Saves your modified and staged changes to a temporary area. |
| `git stash list` | Shows all your saved stashes. |
| `git stash pop` | Applies the latest stash and removes it from the stash list. |
| `git stash apply` | Applies the latest stash but keeps it in the stash list. |
| `git stash drop` | Deletes the latest stash. |

---

## 8. 🔍 Viewing History & Logs
Investigating what happened and when.

| Command | Description |
| :--- | :--- |
| `git log` | Shows the full commit history. |
| `git log --oneline --graph --all` | A highly visual, compact view of the commit tree. |
| `git diff` | Shows unstaged changes between working directory and staging. |
| `git diff --staged` | Shows changes between staging area and last commit. |
| `git show <commit-hash>` | Displays the details (changes, author, date) of a specific commit. |
| `git reflog` | Shows a log of where your HEAD has been (lifesaver if you accidentally delete a branch). |

---

## 9. 🚀 Advanced Operations

| Command | Description |
| :--- | :--- |
| `git rebase <branch>` | Reapplies your commits on top of another branch (linear history). |
| `git rebase -i HEAD~3` | Opens interactive rebase for the last 3 commits (allows squashing, editing, reordering). |
| `git cherry-pick <commit-hash>` | Copies a specific commit from one branch and applies it to your current branch. |
| `git tag -a v1.0 -m "Version 1.0"` | Creates an annotated tag for a release. |
| `git push origin --tags` | Pushes all local tags to the remote repository. |

---

## 🤝 How to Contribute to this Repository
Found a command that's missing? 
1. **Fork** this repository.
2. Create a new branch (`git checkout -b add-new-command`).
3. Commit your changes (`git commit -m 'Add new command'`).
4. Push to the branch (`git push origin add-new-command`).
5. Open a **Pull Request**.

---
*Created with ❤️ for the developer community.*
