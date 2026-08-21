# Lesson 7 – .gitignore and Project Organization

> Notes from the **Goobo Labs Git & GitHub Bootcamp**.

## `.gitignore`

A `.gitignore` file tells Git which files and folders should not be tracked.

It is normally placed in the root of the repository.

Common examples:

```gitignore
# Secrets
.env

# Dependencies
node_modules/

# Build output
dist/
build/

# Logs
*.log

# System files
.DS_Store

# Editor settings
.vscode/
```

### Why Ignore Files?

Files that should usually be ignored include:

* Secrets
* Dependencies
* Build output
* Temporary files
* Logs
* Operating-system files
* Editor-specific files

### Important

`.gitignore` does **not** automatically stop tracking a file that has already been committed.

If a file was accidentally committed:

```bash
git rm --cached .env
```

Then add it to `.gitignore` and commit the change.

## `git rm`

Removes a file and stages the deletion:

```bash
git rm old-file.txt
```

## `git mv`

Renames or moves a file while keeping its Git history connected:

```bash
git mv old-name.md new-name.md
```

## README

A `README.md` is the front door of a repository.

A useful README should explain:

* What the project is
* What it contains
* How to install or set it up
* How to use it
* How others can contribute, when applicable

GitHub automatically displays `README.md` on the repository's main page.

## Repository Organization

A clean project structure makes a repository easier to understand.

Example:

```text
project/
├── .gitignore
├── README.md
├── src/
├── assets/
└── docs/
```

For this project:

```text
git-github-notes/
├── README.md
├── .gitignore
├── notes/
└── .github/
```

### Organization Principles

* Group related files into folders.
* Keep the repository root clean.
* Use clear and consistent names.
* Avoid unnecessary files.
* Make it easy for a new contributor to understand the project.

## Protecting Secrets

Never commit passwords, API keys, tokens, or other sensitive credentials.

Bad:

```javascript
const apiKey = "my-secret-key";
```

Better:

```text
.env
```

and add `.env` to `.gitignore`.

If a secret is accidentally pushed to GitHub, deleting the file is not enough. The exposed credential should be **revoked or rotated**.

## Key Takeaways

* `.gitignore` keeps unwanted files out of Git.
* Create `.gitignore` early.
* `git rm` removes files.
* `git mv` renames or moves files.
* README files explain projects to users and contributors.
* A clean folder structure makes projects easier to maintain.
* Never commit secrets or credentials.
