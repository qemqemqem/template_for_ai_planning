# Knowledge Base

This directory contains accumulated knowledge and insights about the codebase, development process, and technical domain.

## Purpose

Knowledge documents capture learnings, discoveries, and hard-won insights that aren't tied to specific features or decisions but are valuable for anyone working on the codebase. They represent the collective wisdom of the team.

## When to Create a Knowledge Document

Create a knowledge document when:
- Discovering non-obvious patterns or behaviors in the codebase
- Learning valuable insights about technologies used in the project
- Developing troubleshooting approaches for common issues
- Identifying performance characteristics or optimization techniques
- Documenting workflows that aren't captured in other documentation

## Types of Knowledge Documents

### Patterns (`patterns_[topic].md`)
Document recurring design patterns, both those intentionally implemented and those that emerged organically.

### Troubleshooting (`troubleshooting_[topic].md`)
Guides for diagnosing and resolving common issues.

### Best Practices (`best_practices_[topic].md`)
Recommendations for working effectively with specific parts of the codebase or technology stack.

### Technical Insights (`insights_[topic].md`)
Discoveries about how things work that aren't immediately obvious.

### Workflows (`workflow_[topic].md`)
Step-by-step procedures for accomplishing common tasks.

## Template Structures

### Pattern Documentation

```markdown
---
title: [pattern name]
category: pattern
created_date: [YYYY-MM-DD]
last_updated: [YYYY-MM-DD]
tags: [relevant tags]
related_files: [relevant code files]
---

# [Pattern Name]

## Description
Clear explanation of what this pattern is.

## When to Use
Situations where this pattern is appropriate.

## Examples in Codebase
References to where this pattern is used in the project.

## Implementation Guidelines
How to correctly implement this pattern.

## Considerations
Things to be aware of when using this pattern.
```

### Troubleshooting Guide

```markdown
---
title: [problem description]
category: troubleshooting
created_date: [YYYY-MM-DD]
last_updated: [YYYY-MM-DD]
tags: [relevant tags]
affected_components: [parts of the system affected]
---

# [Problem Description]

## Symptoms
Observable signs that indicate this problem.

## Root Causes
Known underlying causes of this issue.

## Diagnostic Steps
1. First step to diagnose
2. Second step
3. ...

## Resolution
Steps to resolve the issue once diagnosed.

## Prevention
How to prevent this issue from occurring.
```

### Technical Insight

```markdown
---
title: [insight description]
category: insight
created_date: [YYYY-MM-DD]
last_updated: [YYYY-MM-DD]
tags: [relevant tags]
discovered_by: [person who discovered this]
verified: [yes/no]
---

# [Insight Title]

## Discovery
Description of the technical insight or non-obvious behavior.

## Context
When or where this insight is relevant.

## Implications
How this insight affects development, performance, or other aspects.

## Verification
How this insight was verified or tested.

## References
Supporting evidence, documentation, or related materials.
```

## Maintenance

- Include "last updated" dates in all knowledge documents
- Periodically review for accuracy and relevance
- Mark outdated information clearly
- Encourage team members to contribute new discoveries
- Cross-reference between related knowledge documents

## Using Knowledge Documents

- Reference knowledge documents in code comments when implementing related patterns
- Include links in design documents when relevant insights inform the design
- Use troubleshooting guides as a first step when encountering known issues
- Share knowledge documents during onboarding to transfer insights efficiently
