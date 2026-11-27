---
name: speckit
description: Entry point for Spec-Driven Development (/speckit). Use when the user invokes /speckit or wants to run the full GitHub Spec Kit workflow (constitution, specify, clarify, plan, tasks, implement, analyze, checklist, converge).
---

# Spec Kit Entry Point (`/speckit`)

Use this skill when the user invokes `/speckit` or asks to start/continue a Spec-Driven Development workflow.

## Available Spec Kit Sub-Skills

Follow the workflow step matching the user's stage by reading the corresponding `SKILL.md`:

1. **Constitution (project principles):** `../speckit-constitution/SKILL.md` (`/speckit-constitution`)
2. **Specification (what & why):** `../speckit-specify/SKILL.md` (`/speckit-specify`)
3. **Clarify ambiguities:** `../speckit-clarify/SKILL.md` (`/speckit-clarify`)
4. **Technical Plan:** `../speckit-plan/SKILL.md` (`/speckit-plan`)
5. **Quality Checklist:** `../speckit-checklist/SKILL.md` (`/speckit-checklist`)
6. **Task Breakdown:** `../speckit-tasks/SKILL.md` (`/speckit-tasks`)
7. **Consistency Analysis:** `../speckit-analyze/SKILL.md` (`/speckit-analyze`)
8. **Implementation:** `../speckit-implement/SKILL.md` (`/speckit-implement`)
9. **Convergence Verification:** `../speckit-converge/SKILL.md` (`/speckit-converge`)

## Routing Rules

- If the user provided a feature idea with `/speckit <idea>`, check whether `.specify/` exists in the workspace (if missing, tell them to run `specify init --here --integration agy --script py` or proceed with `speckit-constitution` / `speckit-specify`).
- Read the exact matching sub-skill's `SKILL.md` and execute it directly.
