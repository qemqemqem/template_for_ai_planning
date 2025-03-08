# Development Checkpoints

This document tracks stable points in development that can serve as rollback targets if needed.

## Current Project
Reference to current feature/issue: [e.g., notes/features/001_example_feature.md]

## Checkpoints

| Date | Git Commit | Description | Status |
|------|------------|-------------|--------|
| YYYY-MM-DD | [hash] | Initial stable implementation of X | active |
| YYYY-MM-DD | [hash] | Completed refactoring of Y component | active |
| YYYY-MM-DD | [hash] | Fixed critical bug in Z functionality | superseded |

## Usage Guidelines

- Record a new checkpoint before starting any significant changes (SP5+)
- Include a descriptive comment that explains what works in this state
- Mark older checkpoints as "superseded" when they're no longer relevant
- Delete checkpoints that are no longer needed to reduce clutter
- Use `git checkout [hash]` to return to a specific checkpoint if needed (but check with the user first)
