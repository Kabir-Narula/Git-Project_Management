
# GitHub & CI/CD Cheat Sheet

## Table of Contents:
1. [GitHub Overview](#github-overview)
2. [Key GitHub Concepts](#key-github-concepts)
   - [Repositories](#repositories)
   - [Branches](#branches)
   - [Commits](#commits)
   - [Pull Requests](#pull-requests)
   - [Forks](#forks)
   - [Issues](#issues)
   - [Tags](#tags)
3. [GitHub Actions Overview](#github-actions-overview)
4. [Core Concepts of CI/CD](#core-concepts-of-ci-cd)
   - [Continuous Integration (CI)](#continuous-integration-ci)
   - [Continuous Delivery (CD)](#continuous-delivery-cd)
   - [Continuous Deployment](#continuous-deployment)
5. [GitHub Actions Key Components](#github-actions-key-components)
   - [Workflows](#workflows)
   - [Jobs](#jobs)
   - [Steps](#steps)
   - [Runners](#runners)
6. [YAML Syntax in GitHub Actions](#yaml-syntax-in-github-actions)
7. [Secrets in GitHub Actions](#secrets-in-github-actions)
8. [Best Practices for GitHub and CI/CD](#best-practices-for-github-and-ci-cd)
9. [Integrating GitHub Actions with Other CI/CD Tools](#integrating-github-actions-with-other-ci-cd-tools)
10. [Common GitHub CI/CD Pipelines](#common-github-ci-cd-pipelines)
11. [Examples](#examples)

---

## GitHub Overview
GitHub is a platform that hosts repositories for version control and collaboration. It allows multiple developers to work on projects simultaneously by managing changes using Git.

---

## Key GitHub Concepts

### Repositories
- A **repository** (or repo) is a project or collection of files that are being worked on.
- Public or private, a repository can include documentation, code, branches, pull requests, and issues.

### Branches
- A **branch** is a parallel version of the repository.
- **Master/Main Branch**: The default branch where the final version of the code is kept.
- Developers typically work on separate branches and merge their changes back into the main branch using pull requests.

### Commits
- A **commit** is a snapshot of changes made to the files in the repository.
- Commits have unique hashes (SHA) and a commit message describing what changes were made.

### Pull Requests
- A **pull request** (PR) is a proposal to merge changes from one branch to another.
- Allows code reviews and discussions before integrating changes.

### Forks
- **Forking** a repository means creating a personal copy of someone else’s repository.
- Forks allow you to experiment with changes before creating pull requests.

### Issues
- **Issues** are used to track tasks, enhancements, and bugs in a project.

### Tags
- **Tags** mark specific points in a repository's history, often used to indicate release versions (e.g., v1.0).

---

## GitHub Actions Overview
**GitHub Actions** is GitHub's CI/CD tool that automates software development workflows. It allows developers to build, test, and deploy code directly from GitHub repositories.

- Workflows are automated based on events like code pushes, pull requests, or issues.
- GitHub Actions uses `.yml` or `.yaml` files to define workflows and tasks.

---

## Core Concepts of CI/CD

### Continuous Integration (CI)
- **CI** ensures that new code commits are frequently merged into the main branch.
- Automated tests and builds are triggered to validate that changes integrate seamlessly.
- The goal is to detect integration issues early.

### Continuous Delivery (CD)
- **CD** automates the process of preparing code for deployment.
- After passing tests, the code is automatically packaged and made ready for deployment, though a manual approval step may be required.

### Continuous Deployment
- **Continuous Deployment** takes CD further by automatically deploying code to production after successful testing, without manual approval.

---

## GitHub Actions Key Components

### Workflows
- A **workflow** is an automated process triggered by events (e.g., push, pull request).
- Defined in a `.yml` file in the `.github/workflows/` directory.
  
### Jobs
- A **job** is a set of steps executed as part of the workflow.
- Jobs can run in sequence or in parallel.

### Steps
- **Steps** are the individual tasks or commands executed as part of a job (e.g., building code, running tests).

### Runners
- A **runner** is a server where the jobs are executed. GitHub provides hosted runners or allows self-hosted runners.

---

## YAML Syntax in GitHub Actions
**YAML** is the format used to define workflows in GitHub Actions. Important elements:
- `name`: Defines the name of the workflow.
- `on`: Specifies the events that trigger the workflow (e.g., `push`, `pull_request`).
- `jobs`: Defines the jobs to be run in the workflow.
- `steps`: Defines individual steps/tasks within a job.

**Example:**

```yaml
name: CI Pipeline

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test
```

---

## Secrets in GitHub Actions
- **Secrets** are used to store sensitive data such as API keys or passwords securely.
- Secrets are accessed using `${{ secrets.<secret_name> }}` in workflows.

---

## Best Practices for GitHub and CI/CD
1. **Branch Naming Conventions**: Use clear naming conventions (e.g., `feature/`, `bugfix/`).
2. **Small, Frequent Commits**: Make small, frequent commits for better traceability.
3. **Test Automation**: Automate tests to catch errors early.
4. **Use CI/CD**: Set up automated pipelines to build, test, and deploy changes.
5. **Review Code**: Use pull requests to review and discuss changes.
6. **Secure Secrets**: Use GitHub secrets to store sensitive data securely.

---

## Integrating GitHub Actions with Other CI/CD Tools
- **Jenkins**, **Travis CI**, and **CircleCI** can be integrated into GitHub for larger or more complex pipelines.
- Webhooks and third-party integrations allow triggering builds or deployments across multiple tools.

---

## Common GitHub CI/CD Pipelines
1. **Node.js CI/CD Pipeline**
   - Uses `npm install` to install dependencies and `npm test` to run tests.
   - Builds the project and deploys it to a cloud provider after tests pass.

2. **Python CI/CD Pipeline**
   - Uses `pip install -r requirements.txt` for dependencies.
   - Runs tests using `pytest` and packages code for deployment.

3. **Docker CI/CD Pipeline**
   - Uses Docker to build images.
   - Pushes the Docker image to a container registry after running tests.

---

## Examples

### Example 1: Basic Node.js Workflow

```yaml
name: Node.js CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test
      - name: Build
        run: npm run build
```

### Example 2: Continuous Deployment Workflow with Docker

```yaml
name: Docker CD

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      - name: Build Docker image
        run: docker build -t myapp:latest .
      - name: Push Docker image to registry
        run: docker push myapp:latest
```

---

## Conclusion
GitHub and CI/CD provide essential tools to streamline software development. GitHub Actions allows developers to automate testing, building, and deployment directly from their repositories, while CI/CD principles ensure smooth and efficient integration of changes. By adopting best practices like secure secrets management, automated testing, and continuous deployment, development teams can achieve faster and more reliable software releases.
