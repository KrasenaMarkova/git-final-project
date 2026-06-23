This is my Git Project

# Git Final Project

This repository demonstrates advanced Git workflows including branching strategies, hotfix management, CI/CD integration, Git hooks, and history recovery using reflog.

---

## Task Overview

This project is divided into three main tasks.

---

# Task 1: Multi-Branch Feature Development and Hotfix Management

## Branching Strategy*
The project uses multiple branches to simulate parallel development:

- `main` – stable production branch
- `feature-auth` – authentication system development
- `feature-dashboard` – UI/dashboard improvements
- `hotfix-security` – urgent security fix
- `legacy-archive` – recovery simulation branch

## Key Operations Performed

- Implemented authentication module (login, logout, base logic)
- Implemented dashboard feature (squash merged into main)
- Introduced and fixed a critical security bug via hotfix branch
- Resolved merge conflict in `config.json`
- Used rebase and squash merge to maintain clean history

## Release Tag

The stable release of the project is marked with:

`v1.0-release`

---

# Task 2: Git Hooks and CI/CD Integration

## Git Hooks

Custom hooks were implemented in `project-hooks/`:

- `pre-commit` → code formatting check (black)
- `commit-msg` → enforces TASK-123 commit format
- `pre-push` → runs unit tests before push

## CI Pipeline

GitHub Actions workflow (`.github/workflows/ci.yml`) includes:

- black formatting check
- pytest execution
- runs on every pull request to `main`

## Validation

- Invalid commit messages are rejected
- Failed tests block pushes
- CI runs automatically on PRs

---

# Task 3: Recovering Lost Work Using git reflog

## Summary
This task demonstrates recovery of lost Git history caused by a simulated force-push scenario. The lost commits were successfully restored using `git reflog`, followed by history cleanup with interactive rebase.

## Recovery Process

- Used `git reflog` to locate lost commits
- Identified commits from deleted history in `legacy-archive`
- Restored branch from commit `aa4bda3`
- Cleaned commit history using `git rebase -i`
- Restored full development flow after simulated force push

## Key Commands Used

- `git reflog`
- `git checkout -b`
- `git rebase -i`
- `git push --force`

---

## Conclusion

This project demonstrates professional Git workflows including:
- Feature branching
- Hotfix management
- CI/CD automation
- Git hooks for validation
- Recovery of lost work using reflog