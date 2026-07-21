# Changelog

> Release history of the Engineering Project Template standard.

This document records the versions of the template itself, not the projects created from its blueprints.

---

# Release History

## [1.0.2] - 2026-07-21

Optional planning fields for the work-package level introduced by Engineering
Playbook 2.3.0. No new blueprint is added and no migration is required for
existing projects.

### Added

* optional Lot level, Level justification and Main risk factors fields in the
  Roadmap blueprint's Planned Work block, with the level initialized to Standard;
* a note stating that, under Engineering Playbook 2.3+, this planned level is
  planning information only and must be confirmed in the development
  contract/prompt, which the Roadmap never replaces.

### Changed

* AI context blueprint guiding agents to the planned level at
  `ROADMAP.md` → Planned Work block → Lot level field, with M03 kept as the sole
  authority for the levels, their criteria and their effects.

---

## [1.0.1] - 2026-07-16

Documentation alignment with Engineering Playbook 2.1.0.

### Added

* documentation grammar rule stating that a document may complement a higher
  authority but never redefine or contradict it;
* agent reminders in the AI context blueprint covering Git context verification
  and the preservation of information that a later step depends on.

### Changed

* Engineering Playbook stated as the sole methodological authority when adopted;
* Claude Code adapter pointing explicitly to the AI context rules it applies;
* single documentary owner for the license in the README blueprint.

---

## [1.0.0] - 2026-07-16

First public release of the Engineering Project Template.

### Added

* lightweight and modular project documentation standard;
* documentation philosophy and grammar;
* official blueprint catalog and usage guide;
* Core, Integration, Project and Advanced blueprint families;
* AI-first progressive documentation navigation;
* execution-based validation, preferring evidence observed by running the
  software over deduction from static analysis, with the available means
  declared by each project;
* optional Engineering Playbook integration.

### Changed

* navigation links made explicit and valid;
* Documentation Grammar scope clarified;
* Engineering Playbook adoption made optional;
* duplicate documentation responsibilities removed;
* blueprint placeholders and initialization instructions standardized;
* technical debt record aligned with explicit origin, impact, risks and resolution conditions.
