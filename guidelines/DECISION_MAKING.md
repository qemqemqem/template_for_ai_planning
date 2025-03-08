# AI Programming Agent Decision-Making Guide

This document provides instructions on how the AI assistant should approach, pace, and make decisions when executing programming tasks. For coding style conventions, see [CONVENTIONS.md](./CONVENTIONS.md). For task complexity estimation, see [STORY_POINTS.md](./STORY_POINTS.md).

## Core Decision-Making Framework

When approaching any task, follow this decision framework:

- **Just do it**: For simple, low-risk changes with clear requirements (typically SP1-SP3)
- **Ask the human first**: When uncertain or multiple valid approaches exist
- **Write a design doc first**: For complex changes, architectural decisions, or when significant tradeoffs exist (typically SP5+)
- **Write tests first**: For most feature implementations and bug fixes
- **Create a feature request first**: When working from unstructured client requirements that need clarification and formalization

If uncertainty exists about which approach to take, err on the side of creating a design doc or asking the human first. It's better to seek guidance than to proceed with an incorrect assumption.

> **Note**: Refer to [STORY_POINTS.md](./STORY_POINTS.md) for detailed guidance on how to approach tasks of different complexity levels.

## Documentation System

The project uses a structured documentation system to maintain context:

- `notes/design_docs/` - Implementation plans for complex features (see [Design Docs Guide](../notes/design_docs/DESIGN_DOCS.md))
- `notes/features/` - Feature specifications and requirements (see [Features Guide](../notes/features/FEATURES.md))
- `notes/issues/` - Bugs and refactoring needs (see [Issues Guide](../notes/issues/ISSUES.md))
- `notes/adr/` - Architecture decision records (see [ADR Guide](../notes/adr/ADR.md))
- `notes/knowledge/` - Discovered insights and patterns (see [Knowledge Guide](../notes/knowledge/KNOWLEDGE.md))
- `notes/working/` - Temporary tracking documents (see Working Documents section)
- `notes/unstructured/` - Initial client requirements (see Unstructured Requirements section)

Reference these documents for context and update them as needed. Each file uses YAML frontmatter for metadata.

## Task Size Estimation

Use story points to estimate task complexity (see [STORY_POINTS.md](./STORY_POINTS.md)). The story point scale helps determine the appropriate approach:

- **SP1-SP2**: Typically "just do it" with minimal documentation
- **SP3-SP5**: Usually require tests first, may need lightweight design notes
- **SP5-SP8**: Require design documentation before implementation
- **SP8+**: Require breaking down into smaller tasks with comprehensive design docs

> **Important**: For detailed guidance on how to handle tasks of different sizes, including special cases like library replacements or paradigm shifts, refer to [STORY_POINTS.md](./STORY_POINTS.md).

## Working Documents

- **Current Goal**: Update `notes/working/current_goal.md` when starting a new task or changing direction. Use this file to track ongoing progress, challenges, and next steps.

- **Checkpoints**: Before making significant changes, record the current git commit hash in `notes/working/checkpoints.md` with a brief description of the stable state. This provides clear rollback points if changes cause unexpected issues.

## Handling Unstructured Requirements

When unstructured client requirements exist in `notes/unstructured/`:
- Prioritize converting them into formal feature requests
- Process these documents by creating structured feature files in `notes/features/`
- As sections are processed, remove them from the unstructured document and add a reference to the new feature file
- Leave cross-references in the unstructured document (e.g., "See: notes/features/001_example_feature.md")
- Continue until all unstructured requirements have been properly formalized

## Code Style

Follow the project's [Coding Style Guide](./CONVENTIONS.md) when writing or modifying code. Prioritize:
- Clear, descriptive naming
- Focused functions with single responsibilities
- Comprehensive error handling
- Comments explaining "why" not "what"
- Readability over cleverness

> **Note**: See [CONVENTIONS.md](./CONVENTIONS.md) for detailed coding standards and best practices.

## Development Approach

- **Test-First Development**: Write tests before implementing features when appropriate
- **Incremental Changes**: Implement one feature at a time with small, focused commits
- **Regular Check-ins**: Pause for human review at logical checkpoints
- **Refactoring**: Only after functionality works correctly and with appropriate test coverage

## Feedback Processing

- Consider feedback carefully rather than implementing immediately
- Document feedback that requires further thought
- Ask clarifying questions when needed
- Sometimes the best response is to think before acting
- Explain reasoning when recommending alternative approaches
