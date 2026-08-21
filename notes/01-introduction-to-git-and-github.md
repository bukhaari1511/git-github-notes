# Lesson 1 – Introduction to Git & GitHub

> Notes from the **Goobo Labs Git & GitHub Bootcamp**.

## What You'll Learn

By completing this lesson, I should be able to:

* Explain what Git is.
* Explain what GitHub is.
* Understand the difference between Git and GitHub.
* Install Git on my computer.
* Configure Git with my name and email.
* Understand how Git and GitHub work together.

## 1. What is Git?

**Git** is a free, open-source, distributed version control system.

It runs on my computer and tracks changes made to a project over time.

Git allows me to create snapshots of my project so that I can:

* Track changes.
* View previous versions.
* Compare changes.
* Work with branches.
* Combine work from different changes.
* Work without an internet connection.

### Key idea

Git keeps the complete history of a project on my local computer.

```text
Project
   ↓
Git
   ↓
Track changes
   ↓
Save snapshots
   ↓
Project history
```

## 2. What is GitHub?

**GitHub** is an online platform that hosts Git repositories.

While Git works locally on my computer, GitHub provides an online place where repositories can be stored and shared.

GitHub also provides collaboration features such as:

* Pull Requests
* Issues
* Code Reviews
* Repository sharing
* Automation with GitHub Actions

## 3. Git vs GitHub

The easiest way to understand the difference:

| Git                        | GitHub                        |
| -------------------------- | ----------------------------- |
| Version control tool       | Online platform               |
| Runs on my computer        | Runs in the cloud             |
| Can work offline           | Usually requires internet     |
| Tracks project history     | Hosts Git repositories        |
| Created by Linus Torvalds  | Owned by Microsoft            |
| Can be used without GitHub | Built around Git repositories |

### Simple explanation

**Git is the tool. GitHub is an online platform that hosts Git repositories and provides collaboration features.**

I can use Git without GitHub.

For example:

```text
My Computer
    │
    └── Git
         │
         ├── Commits
         ├── Branches
         └── History
```

When I want to share my project online:

```text
My Computer
    │
    │ Git
    ▼
  GitHub
    │
    ├── Pull Requests
    ├── Issues
    ├── Code Reviews
    └── GitHub Actions
```

## 4. GitHub Alternatives

GitHub is not the only platform that can host Git repositories.

Other examples include:

* GitLab
* Bitbucket

This bootcamp focuses on **GitHub**.

## 5. Installing Git

Before using Git, I need to check whether it is already installed.

```bash
git --version
```

Example:

```text
git version 2.x.x
```

If Git is not installed, the installation method depends on the operating system.

### Windows

Download Git from:

https://git-scm.com/

### macOS

Using Homebrew:

```bash
brew install git
```

### Debian / Ubuntu

```bash
sudo apt install git
```

### Fedora

```bash
sudo dnf install git
```

After installation, restart the terminal and verify:

```bash
git --version
```

## 6. Configure Git

Before making commits, Git needs to know who I am.

I configure my name:

```bash
git config --global user.name "Your Name"
```

And my email:

```bash
git config --global user.email "you@example.com"
```

The `--global` option means the configuration applies to Git repositories on this computer.

### Check the configuration

```bash
git config --list
```

I should be able to find:

```text
user.name=Your Name
user.email=you@example.com
```

### Why this matters

Git attaches my name and email to my commits.

This makes it possible to identify who created each commit.

For this capstone project, my commits should show my correct identity.

## 7. GitHub Account

To work with GitHub, I need a GitHub account.

The basic steps are:

1. Create a GitHub account.
2. Choose a professional username.
3. Verify the email address.
4. Use the account to host and collaborate on Git repositories.

My GitHub username is:

```text
bukhaari1511
```

## 8. Git and GitHub Workflow

A simple overview of how they work together:

```text
Local Computer
     │
     │ Git
     ▼
Local Repository
     │
     │ git push
     ▼
GitHub Repository
     │
     ├── Pull Requests
     ├── Issues
     ├── Code Reviews
     └── GitHub Actions
```

Git handles the version history locally.

GitHub provides the online collaboration environment.

## 9. Key Takeaways

* Git is a distributed version control system.
* Git runs locally on my computer.
* Git tracks changes and stores project history.
* GitHub hosts Git repositories online.
* Git and GitHub are different things.
* Git can work without GitHub.
* GitHub adds collaboration features around Git.
* Git should be configured with my name and email.
* `git --version` checks whether Git is installed.
* `git config` is used to configure Git.
* GitHub can be used with Pull Requests, Issues, Code Reviews, and GitHub Actions.

## Source

**Goobo Labs — Git & GitHub Bootcamp**

**Lesson 1 – Introduction to Git & GitHub**

https://github.com/goobolabs/git-github-bootcamp/blob/main/lessons/01-introduction-to-git-and-github.md
