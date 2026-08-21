# Lesson 3 – Branching

> Notes from the **Goobo Labs Git & GitHub Bootcamp**.

## What is a Branch?

A **branch** is an independent line of development that allows me to work on changes without directly affecting `main`.

The `main` branch usually represents the trusted version of the project.

Branches are useful for:

* New features
* Bug fixes
* Experiments
* Separate pieces of work
* Team collaboration

```text
main:     A ─── B ─── C
                       \
feature:                D ─── E
```

The feature branch can develop independently while `main` remains unchanged.

## Creating a Branch

The modern way to create and switch to a new branch:

```bash
git switch -c feature-login
```

Older equivalent:

```bash
git checkout -b feature-login
```

## Viewing Branches

```bash
git branch
```

The `*` shows the branch I am currently using.

Example:

```text
* feature-login
  main
```

## Switching Branches

```bash
git switch main
```

```bash
git switch feature-login
```

When switching branches, Git updates the working directory to match that branch.

## Clear Branch Names

Branch names should describe the work being done.

Good examples:

```text
feature-login
feature-contact-form
fix-navbar
update-readme
```

Avoid vague names such as:

```text
test
new
stuff
```

## `git restore`

`git restore` can discard uncommitted changes or unstage a file.

Discard changes:

```bash
git restore notes.txt
```

Unstage a file while keeping its changes:

```bash
git restore --staged notes.txt
```

**Warning:** `git restore <file>` can permanently discard uncommitted changes.

## `git stash`

`git stash` temporarily saves uncommitted work so I can switch branches without committing incomplete work.

```bash
git stash
```

Return to the branch:

```bash
git switch feature-login
```

Restore the saved work:

```bash
git stash pop
```

View saved stashes:

```bash
git stash list
```

## Typical Branch Workflow

```bash
git switch main
git pull
git switch -c feature-new
```

Make changes, then:

```bash
git add .
git commit -m "Add new feature"
```

When finished:

```bash
git switch main
```

The feature can later be brought back into `main` through a merge or Pull Request.

## Key Takeaways

* A branch isolates work from `main`.
* `git switch -c <name>` creates and switches to a branch.
* `git switch <name>` changes branches.
* `git branch` lists branches.
* `git restore` can discard or unstage changes.
* `git stash` temporarily stores unfinished work.
* Clear branch names make collaboration easier.

## Source

**Goobo Labs — Git & GitHub Bootcamp**
**Lesson 3 – Branching**

https://github.com/goobolabs/git-github-bootcamp/blob/main/lessons/03-branching.md
