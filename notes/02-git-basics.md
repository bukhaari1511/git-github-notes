# Lesson 2 – Git Basics

> Notes from the **Goobo Labs Git & GitHub Bootcamp**.

## What is Git?

Git is a **distributed version control system** used to track changes in a project over time.

It allows developers to:

* Track changes
* Save snapshots of their work
* View project history
* Compare changes
* Work with branches
* Return to previous versions

## Git Repository

A **repository** is a project that is tracked by Git.

To create a new local repository:

```bash
git init
```

This creates a hidden `.git` directory containing Git's project history.

## Git's Three Areas

Git uses three main areas:

```text
Working Directory
       ↓
   git add
       ↓
Staging Area
       ↓
  git commit
       ↓
Repository
```

### Working Directory

The files you are currently editing.

### Staging Area

Changes selected for the next commit.

### Repository

The saved history of the project.

## Basic Git Workflow

A typical workflow is:

```bash
git status
git diff
git add .
git diff --staged
git commit -m "Describe the change"
git log --oneline
```

### Important Commands

| Command             | Purpose                                   |
| ------------------- | ----------------------------------------- |
| `git status`        | Shows the current state of the repository |
| `git diff`          | Shows unstaged changes                    |
| `git add`           | Stages changes                            |
| `git diff --staged` | Shows staged changes                      |
| `git commit`        | Saves staged changes                      |
| `git log`           | Shows commit history                      |

## Commits

A **commit** is a snapshot of staged changes.

A good commit should:

* Represent one meaningful change
* Have a clear message
* Be easy to understand from the history

Example:

```bash
git commit -m "docs: add Git basics notes"
```

Good commit messages are specific:

```text
Add Git installation instructions
Fix README setup instructions
Add branching notes
```

Avoid vague messages such as:

```text
update
changes
stuff
```

## Git History

Git records commits as project history:

```text
Commit 1 → Commit 2 → Commit 3 → Commit 4
```

View the history with:

```bash
git log
```

Or use the compact version:

```bash
git log --oneline
```

## Key Takeaways

* Git tracks changes in projects.
* A repository contains a project's Git history.
* `git add` moves changes to the staging area.
* `git commit` saves a snapshot.
* `git status` shows what has changed.
* `git diff` helps review changes.
* `git log` shows commit history.
* Small, meaningful commits make project history easier to understand.

## Source

**Goobo Labs — Git & GitHub Bootcamp**
**Lesson 2 – Git Basics**

https://github.com/goobolabs/git-github-bootcamp/blob/main/lessons/02-git-basics.md
