# Issues Documentation

This directory contains documentation for bugs, issues, and refactoring needs identified in the project.

## Purpose

Issue documents track problems with the existing codebase that need to be addressed, including bugs, technical debt, and refactoring opportunities. They provide a structured way to document, prioritize, and track resolution of these issues.

## Types of Issues

### Bug Reports (`NNN_bug_description.md`)
Problems where the system behaves differently than expected.

### Refactoring Needs (`NNN_refactor_description.md`)
Areas of the codebase that need improvement without changing functionality.

### Technical Debt (`NNN_tech_debt_description.md`)
Compromises made during development that should be addressed.

## When to Create an Issue Document

Create an issue document when:
- A bug is discovered in the system
- Code quality issues are identified that warrant refactoring
- Technical debt is recognized that should be tracked
- Performance problems are identified

## Template Structure for Bugs

```markdown
---
id: [issue ID, e.g. issue-001]
type: bug
status: [identified | in-progress | fixed | verified | closed]
priority: [critical | high | medium | low]
created_date: [YYYY-MM-DD]
affected_components: [parts of the system affected]
reported_by: [person who reported the bug]
assigned_to: [person working on the fix, if any]
story_points: [SP estimate]
fixed_in: [version or commit where fixed]
---

# [Bug Title]

## Description
Clear description of the bug and its impact.

## Steps to Reproduce
1. First step
2. Second step
3. ...

## Expected Behavior
What should happen when following the steps above.

## Actual Behavior
What actually happens when following the steps above.

## Environment
- Relevant environment details (OS, browser, etc.)
- Version information

## Root Cause Analysis
Analysis of what's causing the bug (fill in after investigation).

## Proposed Solution
Approach to fixing the issue (fill in after investigation).

## Related Issues
Links to related issues or bugs.
```

## Template Structure for Refactoring/Technical Debt

```markdown
---
id: [issue ID, e.g. issue-002]
type: [refactor | tech-debt]
status: [identified | planned | in-progress | completed]
priority: [critical | high | medium | low]
created_date: [YYYY-MM-DD]
affected_components: [parts of the system affected]
identified_by: [person who identified the issue]
story_points: [SP estimate]
---

# [Refactoring/Technical Debt Title]

## Description
Clear description of what needs to be refactored and why.

## Current State
How the code currently works and what issues it has.

## Desired State
How the code should work after refactoring.

## Motivation
Why this refactoring is important (e.g., maintainability, performance, readability).

## Impact of Not Addressing
Consequences of leaving this technical debt unresolved.

## Proposed Approach
Recommended way to address this issue.

## Acceptance Criteria
How to verify the refactoring was successful.

## Related Code
Links or references to the specific code that needs refactoring.
```

## Numbering Convention

Issue files should be numbered sequentially using a three-digit number prefix:
- `001_login_validation_bug.md`
- `002_database_query_refactor.md`
- etc.

## Maintenance

- Update issue status as it moves through resolution
- Document any discoveries during investigation
- Link issues to related design documents or features
- Reference issue documents in commit messages when fixing
