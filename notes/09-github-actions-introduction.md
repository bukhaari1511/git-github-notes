# Lesson 9 – GitHub Actions Introduction

> Notes from the **Goobo Labs Git & GitHub Bootcamp**.

## What is CI/CD?

**CI/CD** means Continuous Integration and Continuous Delivery.

### Continuous Integration (CI)

Automatically tests and checks new code as changes are added.

### Continuous Delivery (CD)

Automatically prepares code for release or delivery.

CI/CD helps teams:

* Find problems early
* Save time
* Reduce manual work
* Keep the `main` branch healthy
* Build confidence in changes

## What is GitHub Actions?

**GitHub Actions** is GitHub's built-in automation platform.

It can automatically run tasks when something happens in a repository, such as:

* A push
* A Pull Request
* A schedule
* A manual workflow trigger

No separate server is required for basic workflows.

## GitHub Actions Vocabulary

| Term     | Meaning                                   |
| -------- | ----------------------------------------- |
| Workflow | The complete automation process           |
| Event    | What triggers the workflow                |
| Job      | A group of tasks that run together        |
| Step     | One task within a job                     |
| Runner   | The virtual machine that executes the job |

The basic relationship is:

```text
Event
  ↓
Workflow
  ↓
Job
  ↓
Step
```

## Workflow Files

GitHub Actions workflows are YAML files stored inside:

```text
.github/workflows/
```

Example:

```text
project/
├── .github/
│   └── workflows/
│       └── check.yml
├── README.md
└── notes/
```

## A Simple Workflow

Example workflow:

```yaml
name: Check Project

on: push

jobs:
  check:
    runs-on: ubuntu-latest

    steps:
      - name: Get the code
        uses: actions/checkout@v4

      - name: Check files
        run: |
          echo "Checking project..."
          find . -type f -not -path './.git/*'
```

## `on`

The `on` section defines when the workflow runs.

For example:

```yaml
on: push
```

This runs the workflow whenever code is pushed.

A workflow can also respond to Pull Requests:

```yaml
on:
  push:
  pull_request:
```

## `jobs`

A job groups steps that should run together.

```yaml
jobs:
  check:
    runs-on: ubuntu-latest
```

## `steps`

Steps are individual tasks inside a job.

Example:

```yaml
steps:
  - name: Get the code
    uses: actions/checkout@v4

  - name: Run check
    run: echo "Everything looks good"
```

## `uses` vs `run`

### `uses`

Runs an existing GitHub Action.

```yaml
uses: actions/checkout@v4
```

### `run`

Runs a shell command.

```yaml
run: echo "Hello"
```

Simple way to remember:

```text
uses = use an existing action
run  = execute a command
```

## Repository Variables

GitHub Actions can use repository variables.

For example:

```yaml
env:
  STUDENT_NAME: ${{ vars.STUDENT_NAME }}
```

The variable can be configured in:

**Repository → Settings → Secrets and variables → Actions → Variables**

This avoids hard-coding configurable values inside the workflow.

## Push Workflow

A basic workflow can run whenever code is pushed:

```yaml
on: push
```

This is useful for:

* Running tests
* Checking files
* Checking formatting
* Building projects
* Running automated validation

## Pull Request Checks

A workflow can also run when a Pull Request is opened or updated:

```yaml
on:
  push:
  pull_request:
```

This allows automated checks to provide feedback before changes are merged into `main`.

## Failed Workflows

If a workflow fails:

1. Open the **Actions** tab.
2. Select the failed workflow run.
3. Open the failed job.
4. Read the logs.
5. Identify the error.
6. Fix the problem.
7. Commit and push again.

A successful workflow should show a green check.

## Key Takeaways

* CI/CD automates testing and delivery.
* GitHub Actions provides automation directly inside GitHub.
* Workflows are YAML files stored in `.github/workflows/`.
* Events trigger workflows.
* Jobs contain steps.
* Runners execute jobs.
* `uses` runs an existing action.
* `run` executes shell commands.
* `push` can trigger a workflow automatically.
* Pull Requests can also trigger automated checks.
* The Actions tab provides workflow results and logs.

## Source

**Goobo Labs — Git & GitHub Bootcamp**
**Lesson 9 – GitHub Actions Introduction**

https://github.com/goobolabs/git-github-bootcamp/blob/main/lessons/09-github-actions-introduction.md
