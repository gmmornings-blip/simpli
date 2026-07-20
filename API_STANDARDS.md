# Simpli API Standards

> **Version:** 0.1.0

---

# Philosophy

The API is the contract between Simpli Core, modules, and clients.

It should be:

* Predictable
* Consistent
* Versioned
* Secure
* Well documented

---

# API Style

Primary style:

REST

Future support:

* GraphQL
* WebSockets
* Server-Sent Events

---

# Base URL

```
/api/v1/
```

All endpoints are versioned.

Breaking changes require a new API version.

---

# Resource Naming

Use plural nouns.

Examples:

```
/users
/tasks
/projects
/recipes
/events
```

Avoid verbs in URLs.

---

# HTTP Methods

GET — Retrieve

POST — Create

PUT — Replace

PATCH — Update

DELETE — Remove

---

# Authentication

JWT Bearer Tokens

Future support:

OAuth2

OpenID Connect

API Keys (service integrations)

---

# Standard Response

```json
{
  "success": true,
  "data": {},
  "meta": {},
  "errors": []
}
```

---

# Error Format

```json
{
  "success": false,
  "error": {
    "code": "TASK_NOT_FOUND",
    "message": "Task does not exist."
  }
}
```

---

# Pagination

Standard parameters:

```
?page=1

&page_size=20
```

Response metadata:

* total
* page
* page_size
* total_pages

---

# Filtering

Use query parameters.

Example:

```
?status=completed
```

---

# Sorting

```
?sort=created_at

?order=desc
```

---

# Searching

```
?q=meeting
```

---

# Events

Every important action emits an event.

Examples:

TaskCreated

InvoicePaid

PantryUpdated

BudgetChanged

Events should be descriptive and use PascalCase.

---

# Documentation

Every endpoint includes:

* Purpose
* Parameters
* Authentication
* Example request
* Example response
* Possible errors

---

# Final Principle

An API should feel boring.

If developers have to guess how an endpoint behaves, the API needs improvement.
