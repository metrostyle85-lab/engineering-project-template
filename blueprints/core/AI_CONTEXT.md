# AI Context

> Entry point for AI agents working on this project.

---

## Purpose

Guide AI agents through the project documentation while minimizing unnecessary context.

This document is the official entry point for all AI agents.

---

## Use when

* Starting a new task.
* Understanding the project.
* Looking for project documentation.
* Determining which documents are relevant for the current mission.

---

## Related

* `README.md`
* `PRODUCT_VISION.md` *(if present)*
* `ROADMAP.md` *(if present)*
* `DECISIONS.md` *(if present)*
* `TECH_DEBT.md` *(if present)*
* `ARCHITECTURE.md` *(if present)*
* `SECURITY.md` *(if present)*

---

# Engineering Playbook

Engineering Project Template works on its own. Adopting the Engineering Playbook is optional.

<!-- Replace each value. Set Playbook Adopted to Yes or No. When the project does not adopt the Engineering Playbook, set the remaining values to Not applicable. -->

| Property                     | Value                 |
| ---------------------------- | --------------------- |
| Playbook Adopted             | [Yes or No]           |
| Engineering Playbook Version | [Playbook version]    |
| Repository                   | [Playbook repository] |

When the project adopts the Engineering Playbook, the Playbook becomes the authoritative source for the development methodology, and its rules must not be duplicated in this project.

---

# Reading Strategy

Read only the documentation required for the current mission.

Do not read every document by default.

Use the document grammar to determine whether a document is relevant.

---

# Documentation Navigation

## General understanding

Read:

* `README.md`

---

## Product evolution

Read:

* `PRODUCT_VISION.md` *(if present)*

---

## Planning

Read:

* `ROADMAP.md` *(if present)*

---

## Important decisions

Read:

* `DECISIONS.md` *(if present)*

---

## Technical debt

Read:

* `TECH_DEBT.md` *(if present)*

---

## Technical architecture

Read:

* `ARCHITECTURE.md`

Only if this document exists and the mission requires technical understanding.

---

## Security

Read:

* `SECURITY.md`

Only if this document exists and the mission touches sensitive functionality.

---

# Execution-Based Validation

When the development environment provides a way to run, test or observe the software directly, use it whenever it produces more reliable evidence than a static analysis of the code.

Do not conclude how a feature actually behaves when a reasonably accessible execution can verify it directly.

In development, correction and audit reports, explicitly distinguish results confirmed by execution from deductions based on static analysis.

When a reasonably accessible execution has not been performed, conclusions must not be presented as observed behaviour, but as deductions drawn from analysis.

When a behaviour has been observed by execution, the report must explicitly distinguish it from a mere deduction.

When a behaviour has been reproduced and confirmed in a repeatable manner, it may be presented as confirmed evidence.

<!-- List the execution and observation means actually available in this project, such as an emulator, a real browser and its developer tools, browser automation when available, a local run on the target platform, a local environment, containers, integration tests, or direct execution of commands with representative inputs. Keep only the means that exist and are reasonably accessible. Remove this table if the project offers none. -->

| Means                            | Verifies                    |
| -------------------------------- | --------------------------- |
| [Execution or observation means] | [What it allows to observe] |

---

# Local Project Rules

<!-- Describe only project-specific rules. If the project adopts the Engineering Playbook, do not repeat its rules here. Remove this section if the project defines no specific rules. -->

[Project-specific rules]
