# Documentation Grammar

> Engineering Project Template defines a common grammar for its documentary blueprints.

The objective is to make documentation immediately understandable by both humans and AI agents.

Every documentary blueprint follows the same navigation pattern before presenting its specific content.

---

# Scope

The documentation grammar is normative for the **documentary blueprints** — the Core, Project and Advanced blueprints that carry project documentation.

It does **not** apply to:

* **integration adapters**, such as `CLAUDE.md`;
* the repository's **own documents**: the root `README.md`, the root `AI_CONTEXT.md`, the documents under `docs/`, the root `CHANGELOG.md`, and `LICENSE`.

An integration adapter is intentionally minimal: its single responsibility is to route a specific tool to the project's real entry point. It may therefore omit the standard triptych — Purpose, Use when, Related — and should stay as small as possible.

The repository's own documents follow the conventions that suit their role and are not required to adopt the triptych.

---

# Standard Structure

Every documentary blueprint begins with the following sections:

```markdown
# Document Title

> Short document description.

---

## Purpose

Describe why this document exists.

---

## Use when

Describe when this document should be consulted.

---

## Related

List only directly related documents.

---
```

After these sections, the document presents its own content.

---

# Purpose

The **Purpose** section explains the unique responsibility of the document.

It should answer one question:

> Why does this document exist?

Purpose must remain concise.

---

# Use when

The **Use when** section helps readers decide whether the document is relevant.

It should describe situations rather than implementation details.

If the current task does not match one of these situations, the document can usually be skipped.

---

# Related

The **Related** section connects documents through direct relationships.

It is intentionally limited.

A document should reference only documents that are naturally connected to it.

This creates a progressive navigation graph rather than a complete index.

---

# Design Goals

The documentation grammar is designed to:

* reduce cognitive load;
* avoid duplicated information;
* support progressive reading;
* improve discoverability;
* remain independent of technologies and AI tools.

---

# Navigation Philosophy

Readers should never need to explore the entire documentation.

Each document should naturally guide them toward the next relevant document.

Documentation becomes a navigation system instead of a collection of isolated files.

---

# Good Practices

* Keep the navigation section short.
* Prefer references over duplication.
* Keep responsibilities clearly separated.
* Remove sections that are not applicable.
* Keep documents focused on a single responsibility.

---

# Anti-Patterns

Avoid:

* documents with multiple responsibilities;
* duplicated information;
* long introductions;
* unnecessary sections;
* references to every other document.

Every document should remain focused, concise and easy to navigate.