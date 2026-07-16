# Document Catalog

> Official catalog of the Engineering Project Template blueprints.

This catalog helps select the appropriate blueprint according to the responsibility it fulfills.

---

# Core Blueprints

These documents form the minimal documentation set for every project.

| Blueprint       | Required | Responsibility    |
| --------------- | -------- | ----------------- |
| `README.md`     | Yes      | Human entry point |
| `AI_CONTEXT.md` | Yes      | AI navigation     |

---

# Integration Blueprints

These documents integrate specific tools without becoming part of the project's authoritative documentation.

| Blueprint   | Required | Responsibility      |
| ----------- | -------- | ------------------- |
| `CLAUDE.md` | No       | Claude Code adapter |

---

# Project Blueprints

These documents are added only when the project requires them.

| Blueprint           | Responsibility   | Use when                                                           |
| ------------------- | ---------------- | ------------------------------------------------------------------ |
| `PRODUCT_VISION.md` | Product vision   | The project has functional requirements or long-term goals.        |
| `ROADMAP.md`        | Planning         | Development is organized into phases, milestones or work packages. |
| `DECISIONS.md`      | Decision history | Important decisions should be preserved and justified.             |
| `TECH_DEBT.md`      | Technical debt   | Technical compromises are intentionally accepted or postponed.     |
| `CHANGELOG.md`      | Release history  | The project publishes versions or releases.                        |

---

# Advanced Blueprints

These documents support projects with additional technical or organizational complexity.

| Blueprint         | Responsibility            | Use when                                                             |
| ----------------- | ------------------------- | -------------------------------------------------------------------- |
| `ARCHITECTURE.md` | Technical architecture    | The project contains significant architectural complexity.           |
| `CONTRIBUTING.md` | Contribution process      | Multiple contributors participate in the project.                    |
| `SECURITY.md`     | Project-specific security | The project has dedicated security requirements or sensitive assets. |

---

# Selecting Blueprints

This catalog describes which blueprints exist and what each one is responsible for.

How to select, copy and adapt them is described in [blueprint-guide.md](blueprint-guide.md).

The principles that justify these choices are described in [../philosophy.md](../philosophy.md).