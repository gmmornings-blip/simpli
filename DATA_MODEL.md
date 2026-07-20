# Simpli Data Model

> **Version:** 0.1.0
> **Status:** Conceptual Blueprint

---

# Purpose

The Simpli Data Model defines the shared language of the platform.

Every module should build upon these concepts instead of inventing its own isolated models.

This document intentionally describes **entities and relationships**, not database tables.

Implementation details may evolve.

The concepts should remain stable.

---

# The Life Graph

At the center of Simpli is the **User**.

Everything else either belongs to, relates to, or interacts with the user.

```text
User
│
├── Identity
├── Goals
├── Projects
├── Tasks
├── Calendar
├── Notes
├── Contacts
├── Files
├── Budget
├── Shopping
├── Pantry
├── Recipes
├── Health
├── Business
├── Education
└── AI Memory
```

Every module extends this graph instead of creating disconnected data.

---

# Core Entities

## User

Represents a person using Simpli.

Owns:

* Goals
* Tasks
* Events
* Files
* Preferences
* Health data
* Budgets
* Businesses
* Courses

---

## Goal

A long-term desired outcome.

Examples:

* Save for a car
* Lose weight
* Graduate
* Launch a startup

Goals influence planning across multiple modules.

---

## Project

A collection of related work.

Contains:

* Tasks
* Notes
* Files
* Events
* Contacts

Projects may belong to personal, business, or educational contexts.

---

## Task

A unit of work.

Can belong to:

* Project
* Goal
* Calendar Event
* Course
* Business

Tasks are one of the most connected entities in the platform.

---

## Event

Represents something occurring at a point in time.

Examples:

* Meeting
* Birthday
* Doctor appointment
* Lecture
* Workout
* Payment due

Events populate calendars and may generate reminders.

---

## Contact

Represents a person or organization.

May appear as:

* Client
* Supplier
* Teacher
* Doctor
* Friend
* Family member

One contact, many roles.

---

## File

Any uploaded or generated document.

Examples:

* Images
* PDFs
* Receipts
* Reports
* Assignments

Files may be linked to any entity.

---

## Budget

Represents financial planning.

Contains:

* Accounts
* Income
* Expenses
* Savings
* Categories

Purchases may automatically influence other modules.

---

## Pantry Item

Represents food currently available.

Attributes include:

* Quantity
* Expiry
* Storage location

Pantry items influence recipes and shopping.

---

## Recipe

Represents instructions for preparing food.

Uses:

* Pantry Items
* Shopping Lists
* Nutrition

Recipes consume inventory.

---

## Shopping Item

Represents something intended for purchase.

May originate from:

* Pantry shortages
* Recipes
* Manual entry
* Budget planning

Purchases update inventory automatically.

---

## Health Record

Represents personal wellness information.

Examples:

* Medication
* Weight
* Exercise
* Sleep
* Water intake

Health records contribute to trends and recommendations.

---

## Business

Represents a business owned or managed by the user.

Contains:

* Inventory
* Clients
* Invoices
* Employees
* Payroll
* Scheduling

---

## Course

Represents structured learning.

Contains:

* Lessons
* Assignments
* Flashcards
* Exams
* Attendance

---

# Shared Relationships

Examples of natural relationships:

User → owns → Goals

Goal → contains → Projects

Project → contains → Tasks

Task → appears on → Calendar

Calendar → contains → Events

Recipe → uses → Pantry Items

Pantry Item → added by → Shopping

Shopping → affects → Budget

Budget → contributes to → Goal

Health Record → supports → Goal

Business → generates → Invoices

Invoices → affect → Budget

Course → generates → Assignments

Assignments → become → Tasks

The graph grows through relationships rather than duplication.

---

# Universal Entity Rules

Every entity should support:

* Unique identifier
* Ownership
* Creation date
* Last modified date
* Archive status
* Tags
* Notes
* Attachments
* Permissions
* Audit history

These shared capabilities provide consistency across the ecosystem.

---

# Cross-Module Intelligence

The value of Simpli comes from connected information.

Example:

A grocery purchase:

* reduces available budget,
* updates pantry quantities,
* records spending history,
* refreshes meal suggestions,
* and contributes to nutrition tracking.

One action.

Multiple intelligent updates.

---

# Future Expansion

The Life Graph should support future domains without redesigning the foundation.

Potential additions include:

* Travel
* Vehicles
* Property
* Pets
* Smart Home
* Wearables
* Investments
* Community
* Volunteering
* Sustainability

Every new domain should integrate through relationships with existing entities.

---

# Guiding Principle

Data should never exist in isolation.

Every entity should answer three questions:

1. What is it?
2. Who owns it?
3. How does it connect to the rest of the Life Graph?

If a new entity cannot answer those questions clearly, its design should be reconsidered.

> **In Simpli, relationships create intelligence.**
