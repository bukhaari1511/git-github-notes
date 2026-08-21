# Lesson 6 – Pull Requests and Code Reviews

> Notes from the **Goobo Labs Git & GitHub Bootcamp**.

## What is a Pull Request?

A **Pull Request (PR)** is a request to merge changes from one branch into another.

PRs allow developers to:

* Review changes
* Discuss improvements
* Find bugs
* Share knowledge
* Document what changed and why

## Pull Request Workflow

```text
Create Branch
     ↓
Make Changes
     ↓
Commit
     ↓
Push Branch
     ↓
Open Pull Request
     ↓
Review
     ↓
Merge
     ↓
Delete Branch
```

## Creating a Pull Request

After pushing a branch:

```bash
git push -u origin feature-name
```

Open GitHub and create a Pull Request from:

```text
feature-name → main
```

A good PR description should explain:

```md
## What changed

Describe the changes.

## Why

Explain why the changes were needed.

## How to test

Explain how the changes can be checked.
```

## Code Review

Reviewers inspect the changes in the **Files changed** section.

A review can result in:

| Review          | Meaning                    |
| --------------- | -------------------------- |
| Approve         | Changes are ready to merge |
| Request changes | Changes need to be fixed   |
| Comment         | General feedback           |

Good review comments should be:

* Clear
* Specific
* Respectful
* Focused on the code

## Merge

A branch can be merged into the branch currently checked out:

```bash
git switch main
git merge feature-name
```

On GitHub, a Pull Request can be merged using the **Merge pull request** button.

After merging:

```bash
git switch main
git pull
```

The feature branch can then be deleted.

## Merge Conflicts

A merge conflict happens when Git cannot automatically combine changes, usually because the same lines were changed differently.

Conflict markers look like:

```text
<<<<<<< HEAD
Current version
=======
Incoming version
>>>>>>> feature-name
```

To resolve a conflict:

1. Open the conflicted file.
2. Decide which content should remain.
3. Remove the conflict markers.
4. Stage the resolved file.
5. Commit the resolution.

```bash
git add .
git commit -m "Resolve merge conflict"
```

## Reset vs Revert

### `git reset`

Used to remove a local commit from branch history.

```bash
git reset HEAD~1
```

Use it mainly for commits that have not been shared.

### `git revert`

Creates a new commit that reverses an earlier commit.

```bash
git revert HEAD
```

Use `git revert` for commits that are already shared.

| Situation               | Use          |
| ----------------------- | ------------ |
| Local commit not pushed | `git reset`  |
| Shared commit           | `git revert` |

## PR Best Practices

* Keep PRs small and focused.
* Use one purpose per PR.
* Write a clear title.
* Explain what changed and why.
* Review your own changes before requesting review.
* Respond constructively to feedback.
* Keep review comments specific and respectful.

## Key Takeaways

* A PR proposes changes before they become part of `main`.
* Code review helps improve quality and catch problems.
* Merge conflicts are normal and can be resolved manually.
* `git reset` removes local history.
* `git revert` safely undoes shared changes.
* A professional workflow is:

```text
Branch → Commit → Push → PR → Review → Merge
```
