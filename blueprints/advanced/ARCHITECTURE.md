# Architecture

> Describe the technical structure of the project.

---

## Purpose

Explain how the project is technically organized and how its main components interact.

This document records the current architecture.

It does not replace source code, implementation documentation or decision records.

---

## Use when

* Understanding the technical structure of the project.
* Planning a significant technical change.
* Modifying interactions between major components.
* Reviewing architecture or technical boundaries.
* Onboarding a contributor to a complex project.

---

## Related

* `README.md`
* `DECISIONS.md` *(if present)*
* `TECH_DEBT.md` *(if present)*

---

# Architecture Overview

<!-- Describe the main components, their responsibilities, their relationships and the principal data or control flows. Avoid low-level implementation details. -->

[Architecture overview]

---

<!-- Remove this section if the project is fully self-contained or sufficiently simple. -->

# System Context

<!-- Describe the project within its environment. Include only relevant external actors, systems, services or dependencies. Add a high-level context diagram only if it communicates the structure better than prose. -->

[System context]

---

# Components

<!-- Copy the block below for each significant architectural component. -->

## [Component name]

**Responsibility**

[The component's unique responsibility]

**Interactions**

[Components or external systems it communicates with]

**Boundaries**

[What belongs to this component, and what does not]

---

# Data and Control Flow

<!-- Describe the main flows through the system, such as user requests, data synchronization, authentication or background processing. Use concise diagrams only when they communicate the structure better than prose. -->

[Main flows]

---

<!-- Remove this section if the project does not persist data. -->

# Persistence

<!-- Describe the persistence strategy: data ownership, storage technologies, synchronization boundaries and backup or migration responsibilities. Do not duplicate database schemas or implementation details maintained elsewhere. -->

[Persistence strategy]

---

# External Dependencies

<!-- List only dependencies that influence the architecture. Do not list every package or development dependency. -->

| Dependency | Responsibility                  | Boundary                               |
| ---------- | ------------------------------- | -------------------------------------- |
| [Name]     | [Why the project depends on it] | [What the project assumes or controls] |

---

# Architectural Constraints

<!-- Record constraints that shape the architecture, such as required platforms, offline operation, compatibility, security boundaries or performance. Do not repeat functional constraints already owned by `PRODUCT_VISION.md`. -->

[Architectural constraints]

---

<!-- Remove this section if the project has no explicit validation mechanism. -->

# Architecture Validation

<!-- Describe how the architecture is verified, such as automated tests, dependency rules, static analysis, performance tests or manual review. -->

[Validation mechanisms]
