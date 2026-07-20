# Simpli Engineering Standards

> **Version:** 0.1.0
> **Status:** Living Document

---

# Purpose

Engineering standards ensure that every contribution to Simpli is readable, maintainable, testable, and consistent.

The goal is not to enforce personal preferences, but to reduce friction across the project.

---

# Core Principles

* Clarity over cleverness.
* Consistency over individuality.
* Readability over brevity.
* Simplicity over complexity.
* Reusability over duplication.

---

# Project Structure

Each module should follow a predictable structure.

```text
module/

api/
models/
services/
schemas/
repositories/
events/
tests/
docs/
```

No module should invent its own layout.

---

# Naming Conventions

## Files

Use `snake_case` for Python files.

Use `kebab-case` for frontend component folders.

Examples:

* `user_service.py`
* `budget_repository.py`
* `task-list/`
* `navigation-menu/`

---

## Classes

Use PascalCase.

Examples:

* UserService
* BudgetManager
* NotificationEngine

---

## Functions

Use descriptive `snake_case`.

Good:

* calculate_budget()
* create_invoice()

Avoid abbreviations.

---

## Variables

Names should explain intent.

Prefer:

`remaining_budget`

Over:

`rb`

---

# Git Workflow

Branch names:

* feature/tasks
* feature/pantry
* fix/login
* docs/api
* refactor/search

Never commit directly to `main`.

---

# Commit Messages

Follow Conventional Commits.

Examples:

```
feat(tasks): add recurring task support

fix(auth): resolve token refresh issue

docs(api): update authentication examples

refactor(search): simplify indexing service
```

---

# Documentation

Every public function should be documented.

Every API endpoint documented.

Every module documented.

Architecture changes require documentation updates.

Documentation is part of the feature.

---

# Testing

Every feature includes:

* Unit tests
* Integration tests (where applicable)
* End-to-end tests for user flows

A feature is not complete until it is tested.

---

# Pull Requests

Each pull request should:

* Solve one logical problem
* Include tests
* Update documentation
* Pass CI
* Be reviewed before merging

---

# Code Reviews

Review the code, not the person.

Focus on:

* correctness
* maintainability
* simplicity
* security
* performance

Feedback should educate, not discourage.

---

# Refactoring

Leave the codebase better than you found it.

Small improvements accumulate into long-term quality.

---

# Final Principle

Future contributors should understand your code without needing you to explain it.
