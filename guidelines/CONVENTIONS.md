# Coding Conventions

This document outlines the coding standards and best practices to follow when writing or modifying code. These conventions work in conjunction with the decision-making framework in [DECISION_MAKING.md](./DECISION_MAKING.md) and task complexity guidelines in [STORY_POINTS.md](./STORY_POINTS.md).

## Naming & Structure

- Use descriptive names that explain purpose
- Keep functions focused on a single responsibility
- Group related code together logically
- Follow consistent naming patterns across the codebase

## Documentation

- Document reasoning behind non-obvious decisions, not mechanics
- Explain complex algorithms with step-by-step comments
- Keep commit messages informative and precise
- Reference related documents (features, issues, design docs) in comments

## Code Quality

- Validate inputs at the beginning of functions
- Keep interfaces clean with minimal required parameters
- Choose appropriate data structures for required operations
- Prefer to raise errors and catch them at the outer-most place that is sensible
- Write tests for all new functionality (see [DECISION_MAKING.md](./DECISION_MAKING.md) for when to write tests first)

## Readability

- Prioritize clarity over cleverness
- Use whitespace to improve readability of dense code
- Optimize only after ensuring correctness
- Comment any non-obvious performance improvements

> **Note**: For guidance on when to apply these conventions versus seeking approval first, refer to the complexity guidelines in [STORY_POINTS.md](./STORY_POINTS.md).
