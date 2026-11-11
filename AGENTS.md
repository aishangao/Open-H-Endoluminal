# Project Instructions

## Project Context

- This repository supports Open-H-Endoluminal research and development.
- Current stage: architecture planning and repository initialization.
- The initial goal is synchronized teleoperation data collection, not autonomous navigation.
- Use the root README and project documentation as primary repository context.
- These project rules supplement applicable global instructions; they do not replace higher-priority instructions or expand authorization.

## Context Reading Rules

Before development, read the root README and relevant WP README. Read SYSTEM_ARCHITECTURE.md, INTERFACES.md and DECISIONS.md in 02_Documentation when relevant. Inspect existing implementations and applicable AGENTS.md in affected directories. Simple edits do not require reading the entire repository.

## Development Rules

- Respect existing code and structure; prefer minimal, modular, maintainable implementations.
- Avoid unnecessary dependencies and unrelated refactoring.
- Separate hardware, control, data acquisition and dataset processing responsibilities.
- Do not silently alter established interfaces, units, coordinate frames or data semantics.
- Do not implement unapproved architecture decisions. Mark unresolved details TBD.

## Documentation Rules

### Task-End Impact Check and Updates

After each development task, assess material effects on system architecture, module responsibilities, interfaces/data contracts, approved technical decisions, and WP scope, status, requirements or deliverables. Use task-relevant files and context; do not unnecessarily scan the entire repository.

When justified, automatically make targeted updates within task authorization and applicable scope restrictions:

| Change | Document |
| --- | --- |
| System architecture or module responsibilities | [SYSTEM_ARCHITECTURE.md](02_Documentation/SYSTEM_ARCHITECTURE.md) |
| Interfaces, data formats, units or coordinate frames | [INTERFACES.md](02_Documentation/INTERFACES.md) |
| Significant, explicitly approved technical decisions | [DECISIONS.md](02_Documentation/DECISIONS.md) |
| WP scope, progress, requirements or deliverables | Relevant [WP README](01_Work_Packages/README.md) |
| Project-wide purpose or navigation | [Root README](README.md), if necessary |

Update only affected documents. If a needed update falls outside the authorized scope, report it and request authorization before editing it. Do not rewrite unrelated documentation or add trivial implementation details to the decision log.

### Decision Authority

- Do not independently approve architectural or technical decisions. Record a decision as Approved (or the existing log's Confirmed status) only when explicitly confirmed by the user or established in authoritative project documentation.
- Use Proposed or TBD for unresolved choices; experimental code does not establish an approved design.
- If implementation conflicts with approved documentation, report the conflict and obtain the user's direction before changes that resolve it. Do not silently change documentation to match code.
- Preserve historical decisions; mark replaced decisions Superseded rather than deleting them.

### Documentation Quality and Exceptions

- Keep documentation concise, technically precise and maintainable. Prefer small targeted edits and internal links to authoritative specifications over duplicated detail.
- Distinguish Planned, Implemented and Verified states. Preserve terminology, units, coordinate systems and data semantics; apply the research-integrity rules below to documentation as well.
- No documentation update is required for minor formatting, variable renaming without interface impact, small internal refactoring, ordinary bug fixes without documented-behaviour changes, or unapproved experimental changes, unless another material documented impact justifies it. Unapproved experiments must not be promoted into the approved design.

### On-Demand Documentation Audit

Perform a comprehensive audit only on explicit user request, such as "检查更新项目文档", "Audit project documentation", "检查整个项目的架构和接口文档" or "检查 README 是否需要更新". Respect the requested scope: a project-wide request covers the repository within available access and reasonable resource limits; a single-WP request covers that WP and directly related interfaces and documents.

For the requested scope:

1. Review relevant structure and implementation against approved documentation.
2. Check SYSTEM_ARCHITECTURE.md, INTERFACES.md, DECISIONS.md and relevant WP READMEs; check the root README when relevant.
3. Identify outdated, missing, duplicated or contradictory information. Automatically correct clearly verifiable factual inconsistencies and low-risk omissions within scope, subject to the conflict rule above.
4. Do not change approved decisions or approve new designs without user confirmation. Report unresolved design conflicts and questions requiring user decisions.

Do not run comprehensive audits after ordinary development tasks. Do not create recurring automations, cron jobs, scheduled tasks, periodic scripts, background monitoring or file watchers. Normal task-end impact checks remain enabled.

## Safety and Research Integrity

- Do not treat planned hardware capabilities as tested capabilities or claim hardware safety or experimental validation without evidence.
- Physical robot actuation and potentially hazardous experiments require explicit authorization and applicable safety procedures.
- Never fabricate experimental data, test results or calibration values.
- Distinguish commanded positions from measured positions.
- Proximal motor angles are not directly measured distal endoscope poses.
- UR5 fixture motion is not verified intraluminal insertion depth.

## Data Management

- Never commit large raw recordings or sensitive experimental material by default.
- Preserve timestamps, units, coordinate frames and metadata.
- Keep raw, processed and exported datasets separate.
- Do not publish or upload experimental data without authorization.
- Follow applicable institutional research, privacy and specimen-handling requirements.

## Validation and Reporting

- Verify task-relevant changes before reporting completion; claim tests passed only when they ran.
- Briefly report implementation changes and changed files, tests/validation actually performed, documentation updated, and remaining issues, assumptions or decisions requiring user confirmation.
- If documentation needs no change, state: "Documentation: No update required."
- Do not create commits, push to remotes or modify external systems without explicit authorization.

## Scope Control

Stay within the requested WP or task. Prefer incremental implementation. Do not expand scope or automatically proceed to unrelated work packages without approval. Keep detailed design discussions in documentation and WP files. Do not modify global AGENTS.md or Codex settings, or create additional AGENTS.md files, unless explicitly requested; follow applicable directory-specific rules.
