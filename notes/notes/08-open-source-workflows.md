# Lesson 8 – Open Source Workflows

> Notes from the **Goobo Labs Git & GitHub Bootcamp**.

## What is Open Source?

Open source software is software whose source code is publicly available so people can view, use, modify, and contribute to it.

Open source allows developers to:

* Learn from real projects
* Build a public portfolio
* Contribute improvements
* Work with developer communities
* Gain practical experience

## GitHub Issues

An **Issue** is a tracked item used to report a bug, request a feature, ask a question, or describe a task.

Common issue types:

* Bug
* Feature request
* Documentation
* Task
* Question

A good issue should clearly explain:

* What the problem or request is
* Steps to reproduce, when reporting a bug
* Expected behavior
* Actual behavior
* Relevant environment or screenshots

## Issues vs Discussions

| Issues                        | Discussions             |
| ----------------------------- | ----------------------- |
| Track specific work           | Open-ended conversation |
| Bugs and features             | Questions and ideas     |
| Have a clear completion state | Usually ongoing         |
| Action-oriented               | Conversation-oriented   |

Simple rule:

> **Issues are for tasks. Discussions are for conversations.**

## Contribution Etiquette

Good open-source contributors should:

1. Read the project's `README.md` and contribution guidelines.
2. Search existing issues before creating a new one.
3. Avoid creating duplicate issues.
4. Comment before starting work when required.
5. Be respectful and patient.
6. Keep Pull Requests focused.
7. Accept code-review feedback professionally.

## Typical Open Source Workflow

```text
Find Issue
    ↓
Comment / Claim Work
    ↓
Fork Repository
    ↓
Clone Fork
    ↓
Create Branch
    ↓
Make Changes
    ↓
Commit
    ↓
Push
    ↓
Open Pull Request
    ↓
Code Review
    ↓
Merge
    ↓
Issue Closes
```

## Linking a Pull Request to an Issue

A Pull Request can automatically close an Issue when it is merged.

Use keywords such as:

```text
Fixes #1
```

or:

```text
Closes #1
```

or:

```text
Resolves #1
```

The number must match the actual Issue number.

Example:

```md
## What changed

Added GitHub workflow notes.

## Why

This completes the documentation for the bootcamp lessons.

Fixes #1
```

When the PR is merged, GitHub automatically closes Issue #1.

## Fork vs Clone

A **fork** creates your own GitHub copy of another repository.

A **clone** downloads a repository to your computer.

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

## Good First Issues

A `good first issue` is a small, well-defined task intended for newcomers.

Examples:

* Fix a documentation typo
* Improve a README
* Add a small documentation section
* Fix a simple bug

## Key Takeaways

* Open source allows people to collaborate publicly.
* Issues track actionable work.
* Discussions are better for open-ended conversations.
* Forking creates your own copy of a repository.
* A Pull Request can be linked to an Issue.
* `Fixes #N` can automatically close an Issue when the PR merges.
* Respectful communication is an important part of open source.

## Source

**Goobo Labs — Git & GitHub Bootcamp**
**Lesson 8 – Open Source Workflows**

https://github.com/goobolabs/git-github-bootcamp/blob/main/lessons/08-open-source-workflows.md
