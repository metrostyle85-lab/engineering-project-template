# Security

> Describe project-specific security practices.

---

## Purpose

Document security requirements that are specific to this project.

This document complements the Engineering Playbook.

It does not replace security best practices provided by the project's technology stack.

---

## Use when

* Reviewing the project's security posture.
* Handling sensitive functionality.
* Reporting or resolving security issues.
* Performing a security audit.

---

## Related

* `README.md`
* `ARCHITECTURE.md`
* `DECISIONS.md`

---

# Security Scope

Describe which parts of the project require specific security considerations.

Examples:

* authentication;
* authorization;
* personal data;
* encryption;
* secrets management;
* external integrations.

Remove this section when the project has no specific security concerns.

---

# Security Requirements

Document only project-specific security requirements.

Examples:

* mandatory encryption;
* secure communication;
* access restrictions;
* data retention;
* regulatory requirements.

Do not repeat general security best practices.

---

# Sensitive Assets

Identify the assets requiring protection.

Examples:

* user accounts;
* API keys;
* databases;
* confidential files;
* personal information.

Remove this section when not applicable.

---

# Incident Reporting

Describe how security vulnerabilities should be reported.

Examples:

* private email;
* issue tracker;
* responsible disclosure process.

---

# Security Validation

Describe how security requirements are verified.

Examples:

* manual review;
* penetration testing;
* dependency scanning;
* automated security checks.

Remove this section when no dedicated validation exists.