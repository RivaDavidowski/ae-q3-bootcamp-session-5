# Development Memory System

This directory is the working memory layer for development sessions. It captures discoveries, patterns, and decisions so future work starts with context instead of guesswork.

## Purpose

Use this memory system to track:
- Repeated patterns discovered in code and tests
- Decisions made during implementation and debugging
- Lessons learned from failures, linting issues, and test runs

The goal is to improve consistency, reduce repeated mistakes, and speed up future sessions.

## Two Types of Memory

### 1. Persistent memory
- Location: `.github/copilot-instructions.md`
- Purpose: Foundational principles, workflow standards, and universal project guidance
- Scope: Stable rules that should apply in every session

### 2. Working memory
- Location: `.github/memory/`
- Purpose: Session discoveries, evolving patterns, and active notes
- Scope: Practical, session-driven context that changes over time

Persistent memory defines how we work. Working memory records what we learn while doing the work.

## Directory Structure

- `session-notes.md`: Historical summaries of completed sessions (committed)
- `patterns-discovered.md`: Accumulated implementation and testing patterns (committed)
- `scratch/working-notes.md`: Active session notes and in-progress thinking (not committed)

## How to Use During Workflows

### TDD workflow
- During red-green-refactor cycles, capture quick observations in `scratch/working-notes.md`.
- When a cycle reveals a repeatable strategy (for example, fixture setup shape, assertion style, or mocking boundary), promote it to `patterns-discovered.md`.
- At session end, summarize completed outcomes in `session-notes.md`.

### Linting workflow
- Track lint failures and fixes in `scratch/working-notes.md` while iterating.
- If a lint rule drives a recurring code organization pattern, document it in `patterns-discovered.md`.
- Record final lint outcome and key decisions in `session-notes.md`.

### Debugging workflow
- Log hypotheses, experiments, and results in `scratch/working-notes.md`.
- Convert validated root-cause and fix patterns into `patterns-discovered.md`.
- Capture the final diagnosis and resolution summary in `session-notes.md`.

## How AI Applies Memory in Future Work

1. AI reads persistent memory in `.github/copilot-instructions.md` for baseline behavior.
2. AI references `.github/memory/patterns-discovered.md` for known implementation patterns.
3. AI uses `.github/memory/session-notes.md` for historical context and prior decisions.
4. During active work, AI can write or read `.github/memory/scratch/working-notes.md` for temporary context.

This helps AI provide suggestions aligned with past decisions and proven patterns.

## Session Notes vs Scratch Notes

- `session-notes.md`:
  - For completed session summaries
  - Committed to git as historical record
  - Stable, reviewable timeline of accomplished work

- `scratch/working-notes.md`:
  - For active, in-progress notes
  - Not committed to git
  - Temporary workspace for current task context

Use scratch notes to think and iterate. Use session notes to preserve finalized learnings.
