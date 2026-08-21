# Lesson 5 – Collaboration with GitHub

> Notes from the **Goobo Labs Git & GitHub Bootcamp**.

## Clone

`git clone` creates a complete local copy of an existing remote repository, including its files and history.

```bash
git clone https://github.com/username/project.git
cd project
```

Unlike `git init`, cloning automatically sets up the remote connection as `origin`.

## Clone vs Init

| `git init`               | `git clone`                            |
| ------------------------ | -------------------------------------- |
| Creates a new repository | Copies an existing repository          |
| Starts from scratch      | Starts with existing files and history |
| No remote by default     | `origin` is configured automatically   |

## Fork

A **fork** is your own copy of another person's repository on GitHub.

Forking is normally used when contributing to a repository you do not own.

```text
Original Repository
        ↓
       Fork
        ↓
Your GitHub Repository
        ↓
      Clone
        ↓
Your Computer
```

### Clone vs Fork

* **Clone** happens on your computer.
* **Fork** happens on GitHub.
* Clone gives you a local copy.
* Fork gives you your own GitHub copy.

## Team Collaboration Workflow

A common team workflow is:

```text
Clone
  ↓
Create Branch
  ↓
Make Changes
  ↓
Commit
  ↓
Push Branch
  ↓
Pull Request
  ↓
Review
  ↓
Merge
```

### Golden Rules

* Do not work directly on `main`.
* Use one branch for each feature or fix.
* Pull the latest changes before starting work.
* Push your work regularly.
* Use clear commit messages.
* Keep branches focused.

## Keeping a Branch Updated

Before continuing work:

```bash
git switch main
git pull
git switch feature-name
git merge main
```

This brings the latest `main` changes into the feature branch.

## Rebase

`git rebase main` is another way to update a branch with the latest `main`.

```bash
git switch main
git pull
git switch feature-name
git rebase main
```

### Merge vs Rebase

| Merge                              | Rebase                                   |
| ---------------------------------- | ---------------------------------------- |
| Creates a merge commit when needed | Replays commits on top of `main`         |
| Preserves branch history           | Creates a more linear history            |
| Easier for beginners               | Useful when a team prefers clean history |

Avoid rebasing commits that have already been shared unless the team agrees.

## Key Takeaways

* `git clone` copies an existing repository.
* A fork creates your own GitHub copy.
* Teams normally work with branches instead of committing directly to `main`.
* Pull Requests are used to review and merge branch work.
* `git merge main` and `git rebase main` can update a feature branch.
