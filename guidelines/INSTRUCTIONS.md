# AI Programming Agent Pacing Guide

This document provides instructions on how the AI assistant (aider) should approach, pace, and execute programming tasks.# AI Programming Agent Pacing Guide

This document provides instructions on how the AI assistant (aider) should approach, pace, and execute programming tasks.

## Core Decision-Making Framework

When approaching any task, follow this decision framework:
- **Just do it**: For simple, low-risk changes with clear requirements
- **Ask the human first**: When uncertain or multiple valid approaches exist
- **Write a design doc first**: For complex changes, architectural decisions, or when significant tradeoffs exist
- **Write tests first**: For most feature implementations and bug fixes
- **Create a feature request first**: When working from unstructured client requirements that need clarification and formalization

If uncertainty exists about which approach to take, err on the side of creating a design doc or asking the human first. It's better to seek guidance than to proceed with an incorrect assumption.

## Document Structure & Organization

The AI should leverage the project's file structure to maintain context:
- `notes/design_docs/` for high-level design decisions and goals
- `notes/features/` for feature implementations with numbered IDs
- `notes/issues/` for bugs and issues with numbered IDs
- `notes/working/current_goal.md` as a scratch pad to track the current goal and progress
- `notes/working/checkpoints.md` to track important git commits for potential rollbacks
- `notes/unstructured/` for initial client requirements or unprocessed specifications

The AI should reference these documents for context and update them as needed. Each file uses YAML frontmatter for metadata.

### Using Working Documents

- **Current Goal**: Update `notes/working/current_goal.md` when starting a new task or changing direction. Use this file to track ongoing progress, challenges, and next steps.

- **Checkpoints**: Before making significant changes, record the current git commit hash in `notes/working/checkpoints.md` with a brief description of the stable state. This provides clear rollback points if changes cause unexpected issues.

### Handling Unstructured Requirements

- When unstructured client requirements exist in `notes/unstructured/`, prioritize converting them into formal feature requests
- Process these documents by creating structured feature files in `notes/features/`
- As sections are processed, remove them from the unstructured document and add a reference to the new feature file
- Leave cross-references in the unstructured document (e.g., "See: notes/features/001_example_feature.md")
- Continue until all unstructured requirements have been properly formalized

## Development Pacing & Decision-Making

- Distinguish between decision types:
  - Major decisions require a design document before implementation
  - Minor decisions can be implemented directly with appropriate comments
- Establish tests before writing implementation code
- Implement one feature at a time with small, focused commits
- Pause for human review at logical checkpoints
- Alert the human when making decisions with significant project impact
- Use the story point system defined in the AI Story Points Guide to estimate complexity
- For SP5+ tasks, always create appropriate documentation before implementation
- Refer to the AI Story Points Guide for specific guidance based on task size and type

## Design Decisions

When facing formal Design Decisions (dependencies, architecture, data models, etc.):
- Create a design document in `notes/design_docs/`
- Present multiple alternatives with pros/cons
- Make a clear recommendation with justification
- Get explicit approval before proceeding
- Reference decisions in code comments

## Test-Driven Development

- Write tests before implementing features
- Use small, incremental test cases
- Run tests after each implementation step
- Refactor only after tests pass

## Technical Debt Management

Technical debt should be tracked and managed systematically:

- **Document Refactoring Needs**: Create files in `notes/issues/` with the naming pattern `NNN_example_refactor.md`
- **Include Context**: Document what kind of refactor would be useful and why
- **Prioritize Explicitly**: Assign priority levels to refactoring tasks
- **Link to Code**: Reference specific files, functions, or patterns that need improvement
- **Propose Solutions**: When possible, outline potential approaches to addressing the debt
- **Consider Timing**: Note when refactoring should be addressed (immediately, with related feature work, etc.)

Technical debt should be reviewed regularly, and high-priority items should be addressed proactively rather than waiting for them to cause problems. When implementing new features, check for related technical debt that could be addressed simultaneously.

## Code Organization

- Follow existing project patterns and style
- Prioritize readability over cleverness
- Document assumptions and edge cases
- Create logical abstractions as patterns emerge

## Error Handling

- Add robust error handling from the start
- Consider failure modes during design
- Validate inputs early in functions
- Use appropriate error types and messages

## Refactoring Best Practices

- **Purpose-driven refactoring**: Refactor with a specific goal in mind (e.g., improving readability, reducing complexity, increasing testability)
- **Small, incremental changes**: Make one logical change at a time, commit frequently
- **Test coverage first**: Ensure adequate test coverage before refactoring; add tests if necessary
- **Maintain behavior**: Refactoring should not change the external behavior of the code
- **Document the why**: Explain why the refactoring is needed, not just what changed
- **Separate refactoring from feature work**: Avoid mixing refactoring with feature changes in the same commit
- **Prioritize impact**: Focus on refactoring high-traffic or error-prone areas first
- **Watch for scope creep**: Resist the temptation to fix "one more thing" — stay focused
- **Refactor in pairs**: For complex refactoring, get explicit approval or review from the human

If a refactoring seems large or risky, create a design document outlining the approach, risks, and rollback strategy before proceeding.

## Communication Style

- Explain planned approach before coding
- Summarize changes after implementation
- Highlight areas of uncertainty
- Present alternatives for key decisions

## Documentation

- Update documentation alongside code changes
- Include usage examples in docstrings
- Document known limitations
- Add comments for complex logic

## Performance Considerations

- Focus on correctness first, optimization later
- Profile before optimizing
- Explain performance tradeoffs
- Use appropriate data structures for expected scale

## Research vs. Implementation

- Research solutions before implementation for unfamiliar problems
- Note that choosing dependencies is typically a Design Decision
- For library vs. custom implementation:
  - Prefer existing, well-maintained libraries
  - Present alternatives with pros/cons
  - Get explicit approval before proceeding

## Handling Ambiguous Requirements

- Ask clarifying questions when requirements are unclear
- Present multiple interpretations when ambiguity exists
- When requirements conflict:
  - Identify and explain the conflict
  - Analyze tradeoffs and offer recommendations
  - Ask for explicit direction
  - Document the decision

## Project-Specific Understanding

- Begin by identifying key components and architecture
- Document observations about project patterns
- Build knowledge incrementally
- Note when recommendations might need context adjustment

## Feedback Incorporation

- Consider feedback carefully rather than implementing immediately
- Document feedback that requires further thought
- Ask clarifying questions when needed
- Sometimes the best response is to think before acting
- Explain reasoning when recommending alternative approaches
