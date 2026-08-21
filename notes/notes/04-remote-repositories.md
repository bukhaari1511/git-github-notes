# Lesson 4 – Remote Repositories

> Notes from the **Goobo Labs Git & GitHub Bootcamp**.

## Local vs Remote Repository

A **local repository** is the Git repository on my computer.

A **remote repository** is a copy of the repository hosted on a server such as GitHub.

| Local Repository           | Remote Repository         |
| -------------------------- | ------------------------- |
| Lives on my computer       | Lives on a server         |
| Used for daily development | Shared online copy        |
| Can work offline           | Requires internet access  |
| Private unless shared      | Can be shared with others |

## Why Use a Remote Repository?

A remote repository provides:

* **Backup** — protects the project if my computer fails.
* **Sharing** — allows others to access the project.
* **Collaboration** — team members can synchronize their work.
* **Portfolio** — projects can be displayed on GitHub.

```text
My Computer                         GitHub
     │                                │
     │           git push             │
     ├───────────────────────────────►│
     │                                │
     │           git pull             │
     │◄───────────────────────────────┤
     │                                │
 Local Repository              Remote Repository
```

## Connecting a Local Repository to GitHub

First, create an empty repository on GitHub.

Then connect the local repository:

```bash
git remote add origin https://github.com/username/project.git
```

`origin` is the conventional name for the main remote repository.

Check the connection:

```bash
git remote -v
```

Example:

```text
origin  https://github.com/username/project.git (fetch)
origin  https://github.com/username/project.git (push)
```

## Changing the Remote URL

If the repository URL changes:

```bash
git remote set-url origin https://github.com/username/new-project.git
```

Then verify:

```bash
git remote -v
```

## `git push`

`git push` uploads committed local changes to the remote repository.

First push:

```bash
git push -u origin main
```

After the branch is connected:

```bash
git push
```

Important:

> `git push` only uploads commits. Uncommitted changes are not pushed.

## `git pull`

`git pull` downloads changes from the remote and integrates them into the current local branch.

```bash
git pull
```

Conceptually:

```text
git pull = git fetch + git merge
```

A good habit is to pull before starting work when working with a shared repository.

## `git fetch`

`git fetch` downloads information about changes from the remote without merging those changes into the current branch.

```bash
git fetch
```

This allows me to inspect remote changes before deciding what to do with them.

## Pull vs Fetch

| `git fetch`                               | `git pull`                 |
| ----------------------------------------- | -------------------------- |
| Downloads remote changes                  | Downloads remote changes   |
| Does not merge them                       | Merges them                |
| Does not immediately change working files | Updates the current branch |
| Useful for reviewing first                | Useful for synchronizing   |

Simple rule:

```text
git fetch = download and inspect
git pull  = fetch + integrate
```

## Complete Remote Workflow

```bash
git pull
```

Make changes, then:

```bash
git add .
git commit -m "Describe the change"
git push
```

The complete flow:

```text
Working Directory
       │
    git add
       ↓
Staging Area
       │
  git commit
       ↓
Local Repository
       │
   git push
       ↓
GitHub Remote
       │
   git pull
       ↓
Local Repository
```

## Key Takeaways

* A local repository lives on my computer.
* A remote repository is hosted online.
* `origin` is the conventional name for the main remote.
* `git remote -v` shows remote connections.
* `git push` uploads commits.
* `git pull` downloads and integrates remote changes.
* `git fetch` downloads remote information without merging.
* A remote repository provides backup, sharing, collaboration, and portfolio benefits.

## Source

**Goobo Labs — Git & GitHub Bootcamp**
**Lesson 4 – Remote Repositories**

https://github.com/goobolabs/git-github-bootcamp/blob/main/lessons/04-remote-repositories.md
