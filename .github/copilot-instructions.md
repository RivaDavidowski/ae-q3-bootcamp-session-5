# Copilot Instructions

## Purpose

Provide shared, persistent project guidance for AI-assisted development across this workspace.

## Agent Usage

- Use project documentation in `docs/` as the source of truth for implementation context.
- Prioritize test-first changes for backend and frontend behavior updates.
- Keep code changes scoped to the current task and avoid unrelated refactors.
- Validate with relevant tests and lint checks before finalizing suggestions.

## Memory System

- Persistent Memory: This file (`.github/copilot-instructions.md`) contains foundational principles and workflows
- Working Memory: `.github/memory/` directory contains discoveries and patterns
- During active development, take notes in `.github/memory/scratch/working-notes.md` (not committed)
- At end of session, summarize key findings into `.github/memory/session-notes.md` (committed)
- Document recurring code patterns in `.github/memory/patterns-discovered.md` (committed)
- Reference these files when providing context-aware suggestions
