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
* `DECISIONS.md`
* `TECH_DEBT.md`

---

# Architecture Overview

Provide a concise overview of the system.

Describe:

* the main components;
* their responsibilities;
* their relationships;
* the principal data or control flows.

Avoid low-level implementation details.

---

# System Context

Describe the project within its environment.

Include only relevant external actors, systems, services or dependencies.

```text
[Optional high-level context diagram]
```

Remove this section when the project is fully self-contained or sufficiently simple.

---

# Components

Document each major component.

## [Component Name]

**Responsibility**

[Describe the component’s unique responsibility.]

**Interactions**

[Describe which components or external systems it communicates with.]

**Boundaries**

[Describe what belongs to this component and what does not.]

Repeat only for significant architectural components.

---

# Data and Control Flow

Describe the main flows through the system.

Examples:

* user request flow;
* data synchronization flow;
* authentication flow;
* background processing flow;
* media or event flow.

Use concise diagrams when they communicate the structure better than prose.

```text
[Optional flow diagram]
```

---

# Persistence

Describe the persistence strategy when relevant.

Include:

* data ownership;
* storage technologies;
* synchronization boundaries;
* backup or migration responsibilities.

Do not duplicate database schemas or implementation details maintained elsewhere.

Remove this section when the project does not persist data.

---

# External Dependencies

List only dependencies that influence the architecture.

| Dependency | Responsibility                  | Boundary                               |
| ---------- | ------------------------------- | -------------------------------------- |
| [Name]     | [Why the project depends on it] | [What the project assumes or controls] |

Do not list every package or development dependency.

---

# Architectural Constraints

Record constraints that shape the architecture.

Examples:

* required platforms;
* offline operation;
* compatibility requirements;
* security boundaries;
* performance or availability constraints.

Do not repeat functional constraints already owned by `PRODUCT_VISION.md`.

---

# Architecture Validation

Describe how the architecture is verified when necessary.

Examples:

* automated tests;
* dependency rules;
* static analysis;
* performance tests;
* manual architectural review.

Remove this section when no explicit validation mechanism exists.