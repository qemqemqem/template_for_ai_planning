# AI Development Story Points Guide

This document defines story point values for AI-assisted development and provides guidance on how to approach tasks of different sizes and types. This guide works in conjunction with the [DECISION_MAKING.md](./DECISION_MAKING.md) and [CONVENTIONS.md](./CONVENTIONS.md) documents.

## Story Point Definitions for AI Development

Story points measure complexity, uncertainty, and effort rather than time. For AI development, we use the Fibonacci scale (1, 2, 3, 5, 8, 13, 21). These estimates help determine the appropriate decision-making approach as outlined in [DECISION_MAKING.md](./DECISION_MAKING.md).

## Story Point Scale

### 1 Point (SP1) - Trivial Change
- **Characteristics**: Single edit in one file, confined to a few lines
- **Examples**: Typo fix, simple constant change, minor text update
- **Approach**:
  - **Bug Fix**: Just fix it with a clear commit message
  - **Feature**: Implement directly if requirements are crystal clear
  - **Refactor**: Proceed if completely isolated and risk-free

### 2 Points (SP2) - Simple Change
- **Characteristics**: Multiple edits but still confined to one file
- **Examples**: Adding a simple method, updating a function, adding basic validation
- **Approach**:
  - **Bug Fix**: Write test first if possible, then implement
  - **Feature**: Implement directly and then explain in comments
  - **Refactor**: Document intent in comments, implement with tests if possible

### 3 Points (SP3) - Standard Change
- **Characteristics**: Changes spanning 2-3 files within the same component
- **Examples**: Adding a straightforward API endpoint, extending an existing feature
- **Approach**:
  - **Bug Fix**: Write test that reproduces bug, fix, verify
  - **Feature**: TDD approach, implement incrementally
  - **Refactor**: Document approach in comments, seek confirmation from user if uncertain

### 5 Points (SP5) - Moderately Complex Change
- **Characteristics**: Changes affecting multiple files across different components
- **Examples**: Adding a feature requiring updates to multiple layers, moderate data model change
- **Approach**:
  - **Bug Fix**: Create a document in `notes/issues`, get approval
  - **Feature**: Create a document in `notes/features`, get approval
  - **Refactor**: Document approach with before/after examples, create a doc in `notes/issues`, get approval

Everything above SP5 requires both a design document and explicit approval before proceeding. The document should go in `notes/issues`, `notes/features`, or `notes/design_docs` as appropriate.

### 8 Points (SP8) - Complex Change
- **Characteristics**: Significant changes affecting many components
- **Examples**: Adding a complex feature, moderate architectural changes
- **Approach**:
  - **Bug Fix**: Create detailed issue document with fix options
  - **Feature**: Create design doc with approach options, use TDD
  - **Refactor**: Always create design doc in `notes/design_docs`, get explicit approval
  - **Library Swap**: Create migration plan with fallback options

### 13 Points (SP13) - Very Complex Change
- **Characteristics**: Major changes with substantial architectural implications
- **Examples**: Introducing new subsystem, complex algorithm implementation
- **Approach**:
  - **Feature**: Detailed design doc required, break into smaller tasks
  - **Refactor**: Comprehensive design doc with risk assessment required
  - **Class Rewrite**: Create design doc with interface compatibility analysis

### 21 Points (SP21) - Epic Change
- **Characteristics**: Extensive changes affecting the entire system
- **Examples**: New major feature set, architectural overhaul, paradigm shift
- **Approach**:
  - **Any Type**: Must be broken down into smaller stories
  - Always create comprehensive design doc
  - Seek explicit approval on approach before starting
  - Consider implementation in phases
  - **Paradigm Change**: Requires prototype and extensive discussion

## Special Case Guidance

### Library Replacement (typically SP8-SP13)
- Create a design document that includes:
  - Justification for replacement
  - Feature comparison between old and new libraries
  - Migration strategy with incremental steps
  - Testing approach for verifying equivalent functionality
  - Rollback plan in case of issues
- Implement a proof-of-concept first
- Create a complete test suite before major changes
- Consider a parallel implementation period if possible

### Class Rewrite (typically SP8-SP13)
- Create a design document covering:
  - Interface analysis (what depends on this class?)
  - Behavioral specifications to preserve
  - Proposed new implementation with justification
  - Migration approach for dependent code
- Consider the strangler pattern for gradual replacement
- Implement comprehensive tests before rewriting
- Plan for a verification period where both implementations coexist if possible

### Paradigm Shift (typically SP13-SP21)
- Always requires a detailed design document including:
  - Problem statement explaining why current paradigm is insufficient
  - Detailed explanation of proposed new paradigm
  - Concrete examples showing before/after
  - Migration strategy with estimated effort
  - Training/knowledge sharing plan
- Create a prototype implementation for evaluation
- Plan for incremental adoption rather than big-bang changes
- Break down into multiple smaller stories after approval
- Document decision in architecture decision records

## Breaking Down Large Tasks

When encountering tasks estimated at SP8 or above:
1. Look for components that can be implemented independently
2. Identify core vs. extended functionality
3. Consider vertical slices that deliver end-to-end value
4. Create dependencies between smaller stories
5. Document the breakdown approach and get approval

> **Reference**: For complex tasks, follow the design document approach outlined in [DECISION_MAKING.md](./DECISION_MAKING.md) under "Documentation System".

## Task Expansion Risk

Be aware that tasks initially estimated as small (SP1-SP3) may expand during implementation. If you discover a task is more complex than initially estimated:
1. Stop and reassess
2. Document the newly discovered complexity
3. Consider whether to continue or seek further guidance
4. Update the estimate and approach accordingly

> **Important**: When task complexity increases, revisit the decision-making framework in [DECISION_MAKING.md](./DECISION_MAKING.md) to determine if you should switch from "just do it" to "ask the human first" or "write a design doc first".
