# Technical Debt

> Track technical debt that has been consciously accepted.

---

## Purpose

Record technical debt that has been intentionally accepted or postponed.

This document explains **what** the debt is and **why** it has not yet been resolved.

Only intentional technical debt belongs here.

---

## Use when

* Postponing technical work.
* Recording a known limitation.
* Preparing a release.
* Planning future refactoring.

---

## Related

* `ROADMAP.md`
* `DECISIONS.md`
* `CHANGELOG.md`

---

# Debt Register

Each entry should follow the structure below.

---

## TD-001 — Debt Title

| Property | Value                                                                          |
| -------- | ------------------------------------------------------------------------------ |
| Status   | Open / Resolved                                                                |
| Priority | Low / Medium / High / Critical                                                 |
| Category | Architecture / Code / Documentation / Performance / Security / Testing / Other |
| Date     |                                                                                |
| Owner    |                                                                                |

### Origin

Describe the technical compromise and how it arose (the decision, constraint or deadline that introduced the debt).

### Reason

Explain why the debt was consciously accepted or postponed instead of being resolved now.

### Impact

Describe the effects the debt has on the project today.

### Risks

Describe what could go wrong if the debt remains unresolved, including likelihood and severity.

### Resolution Conditions

Describe the conditions or triggers that should prompt resolving the debt.

### Resolution Strategy

Describe the intended approach to resolve the debt.

---

## TD-002

Repeat the same structure for each additional debt.

---

# Resolved Debt

Move resolved entries here instead of deleting them.

Keep the project history intact.