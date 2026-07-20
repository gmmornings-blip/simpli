# Simpli Technology Stack

> **Version:** 0.1.0
> **Status:** Living Document

---

# Purpose

This document defines the official technology choices for Simpli.

Its purpose is to ensure consistency across the project, prevent unnecessary technology changes, and provide clear guidance for contributors.

Technology should only change when there is a measurable architectural or business benefit.

---

# Technology Principles

When selecting technologies, Simpli follows these priorities:

1. Open source first.
2. Stable over trendy.
3. Well documented.
4. Large community support.
5. Long-term maintainability.
6. Cross-platform compatibility.
7. Minimal vendor lock-in.

---

# Frontend

## Framework

**Next.js (React + TypeScript)**

Why:

* Mature ecosystem
* Server-side rendering
* Excellent developer experience
* Large community
* Easy deployment
* Strong long-term support

Alternatives considered:

* SvelteKit
* Nuxt
* Angular

Decision:

Next.js remains the official frontend framework.

---

# Mobile

## Framework

**React Native + Expo**

Why:

* Shared TypeScript knowledge
* Cross-platform
* Fast development
* Strong ecosystem

Future:

Native platform features may be added when necessary.

---

# Backend

## Framework

**FastAPI**

Language:

Python

Why:

* High performance
* Automatic API documentation
* Excellent typing
* AI ecosystem compatibility
* Clean architecture

Alternatives:

* Django
* NestJS
* ASP.NET Core
* Go Fiber

Decision:

FastAPI is the official backend platform.

---

# Database

## Primary Database

PostgreSQL

Why:

* Reliability
* ACID compliance
* Advanced indexing
* JSON support
* Excellent performance

This is Simpli's primary data store.

---

# ORM

SQLAlchemy

Reason:

* Mature
* Flexible
* Well maintained
* Excellent migration support

---

# Authentication

Phase 1

JWT Authentication

Future

OAuth2

OpenID Connect

Enterprise identity providers

Authentication should remain provider-agnostic.

---

# Caching

Redis

Uses:

* Sessions
* API caching
* Background jobs
* Rate limiting

---

# Search

Meilisearch

Reason:

Simple

Fast

Developer friendly

Future:

Optional Elasticsearch adapter.

---

# Object Storage

MinIO

Reason:

S3 compatible

Open source

Self-hostable

---

# AI Layer

Ollama

Supported Models

* Llama
* Qwen
* Gemma
* Mistral

Future providers may include OpenAI-compatible APIs, but the platform should remain model-agnostic.

---

# Background Processing

Celery

Broker

Redis

Purpose

Long-running jobs

Notifications

Imports

Exports

AI tasks

---

# Web Server

Uvicorn

Production

Gunicorn + Uvicorn Workers

---

# API Style

REST

Future

GraphQL gateway

WebSockets

Server-Sent Events

gRPC (internal services if needed)

---

# Containerization

Docker

Docker Compose

Future

Kubernetes

---

# Version Control

Git

Hosting

GitHub

Branch Strategy

main → stable

develop → active development

feature/* → new work

fix/* → bug fixes

release/* → releases

---

# Testing

Backend

pytest

Frontend

Vitest

End-to-end

Playwright

---

# Documentation

Markdown

MkDocs

OpenAPI (automatic)

Architecture diagrams

Every public API must be documented.

---

# Code Formatting

Python

Black

isort

ruff

JavaScript / TypeScript

Prettier

ESLint

Formatting is automated.

Manual formatting should never be necessary.

---

# CI/CD

GitHub Actions

Every Pull Request should automatically:

* Lint
* Test
* Build
* Validate documentation

---

# Monitoring

Prometheus

Grafana

Loki

Monitoring is considered part of the platform—not an optional extra.

---

# Security

Secrets are never committed.

Environment variables are required.

HTTPS in production.

Dependency updates reviewed regularly.

Security audits scheduled periodically.

---

# Dependency Policy

Dependencies should be:

* actively maintained
* widely adopted
* permissively licensed
* replaceable

Avoid introducing libraries for problems that can be solved simply.

---

# Technology Evolution

Technology will evolve.

Our architecture should make replacing a framework easier than rewriting the platform.

Frameworks are tools.

The architecture is the product.
