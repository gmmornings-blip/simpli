# Simpli Architecture

> **Version:** 0.1.0
> **Status:** Living Document

---

# Introduction

Simpli is not a collection of separate applications.

It is a single ecosystem composed of independent but connected modules built on one shared foundation.

The architecture is designed around one fundamental belief:

> **Every piece of information should have a single source of truth and be reusable throughout the ecosystem.**

This document defines how Simpli is structured and how future contributors should think about building within it.

---

# Architecture Philosophy

Simpli follows six architectural principles.

## 1. Modular

Every major capability is developed as an independent module.

Examples include:

* Tasks
* Budget
* Pantry
* Recipes
* Health
* Inventory
* Education

Modules should be removable, replaceable, and expandable without affecting unrelated modules.

---

## 2. Shared Foundation

All modules inherit common platform services.

These services are collectively known as **Simpli Core**.

Simpli Core provides:

* Authentication
* Authorization
* User Profiles
* Notifications
* Calendar
* Search
* File Storage
* AI Gateway
* Logging
* Settings
* API Gateway
* Analytics
* Audit Logs

No module should duplicate these capabilities.

---

## 3. Connected by Design

Modules should communicate through shared domain models rather than isolated copies of data.

For example:

A grocery purchase should update:

* Budget
* Pantry
* Shopping History
* Nutrition
* Recipe Suggestions

without requiring duplicate user input.

Connections between modules create the value of the ecosystem.

---

## 4. Single Source of Truth

Every type of information has one authoritative location.

Examples:

User information exists only once.

Products exist only once.

Tasks exist only once.

Recipes exist only once.

Other modules reference these records instead of copying them.

---

## 5. API First

Every feature must be accessible through APIs.

Benefits include:

* Web applications
* Mobile applications
* Desktop applications
* Future integrations
* Third-party plugins
* AI services

All consume the same backend services.

---

## 6. Open and Extensible

Future developers should be able to create new modules without modifying the platform itself.

Adding a module should feel like installing a new capability rather than rewriting the system.

---

# High-Level Architecture

```
                    Simpli Platform

                 ┌───────────────────┐
                 │    Web Client     │
                 ├───────────────────┤
                 │   Mobile Client   │
                 ├───────────────────┤
                 │   Desktop Client  │
                 └─────────┬─────────┘
                           │
                   API Gateway
                           │
        ┌─────────────────────────────────┐
        │          Simpli Core            │
        │ Authentication                  │
        │ Authorization                   │
        │ Search                          │
        │ Notifications                   │
        │ Calendar                        │
        │ Files                           │
        │ AI Gateway                      │
        │ Logging                         │
        └─────────────────────────────────┘
                           │
       ┌─────────────────────────────────────┐
       │            Modules                  │
       │ Life │ Business │ Health │ School   │
       └─────────────────────────────────────┘
                           │
                  PostgreSQL Database
```

---

# Simpli Core

Simpli Core is the backbone of the ecosystem.

Every module depends on it.

Responsibilities include:

* Identity management
* Permissions
* Shared UI
* Common APIs
* User preferences
* Notifications
* Search
* File management
* AI communication
* Shared utilities

Core should remain stable.

Business logic belongs inside modules.

---

# Modules

A module is a self-contained capability.

Each module should contain:

* Database models
* Business logic
* API endpoints
* User interface
* Documentation
* Tests

Modules should expose clear interfaces and avoid direct dependencies on each other.

Communication should occur through shared services or published events.

---

# The Simpli Life Graph

The heart of Simpli is the **Life Graph**.

Instead of treating information as isolated tables, Simpli models relationships between concepts.

Example:

```
User
│
├── Tasks
├── Calendar
├── Goals
├── Budget
├── Pantry
├── Recipes
├── Journal
├── Business
├── School
└── Health
```

Each object may relate to many others.

Example:

Recipe

↓

Uses Ingredients

↓

Ingredients exist in Pantry

↓

Pantry affects Shopping

↓

Shopping affects Budget

↓

Budget affects Savings Goal

↓

Savings affects Financial Planning

Information flows naturally through relationships rather than duplication.

---

# Event-Driven Automation

Modules should communicate using events.

Example:

Receipt Scanned

↓

Expense Created

↓

Budget Updated

↓

Pantry Updated

↓

Shopping History Updated

↓

Recipe Recommendations Refreshed

Each module reacts independently.

No module should tightly control another.

---

# Directory Structure

```
simpli/

apps/
    web/
    mobile/
    desktop/

backend/
    core/
    gateway/

modules/
    tasks/
    budget/
    pantry/
    recipes/
    inventory/
    education/
    health/

packages/
    ui/
    shared/
    utils/

docs/

docker/

scripts/

tests/
```

---

# Coding Standards

Every contribution should follow these principles.

* Readability over cleverness.
* Explicit over implicit.
* Small functions.
* Small commits.
* Clear naming.
* Comprehensive documentation.
* Automated testing.
* Consistent formatting.

Future maintainers should understand the code without guessing.

---

# Security Principles

Security is built into the architecture.

* Least privilege access
* Secure authentication
* Encrypted communication
* Input validation
* Audit logging
* Privacy by default

Security should never be treated as an afterthought.

---

# Artificial Intelligence

Artificial Intelligence is a platform service.

It is not the platform.

AI should:

* Reduce repetitive work.
* Explain recommendations.
* Respect user privacy.
* Never make irreversible decisions automatically.
* Enhance modules rather than replace them.

Users remain in control.

---

# Future Expansion

The architecture should support future additions such as:

* Plugins
* Community-developed modules
* IoT integrations
* Wearable devices
* Smart home automation
* Voice assistants
* Cloud synchronization
* Offline-first functionality

The foundation should remain stable while capabilities evolve.

---

# Final Thought

Every architectural decision should answer one question:

> **Does this make Simpli simpler to build, simpler to maintain, and simpler to use?**

If not, reconsider the design.

Our goal is not to build the biggest platform.

Our goal is to build the clearest one.
