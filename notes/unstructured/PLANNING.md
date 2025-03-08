# Unstructured Requirements Management

This directory (`notes/unstructured`) serves as a temporary holding area for raw project requirements, client specifications, and other unprocessed documentation that needs to be formalized.

## Purpose

Unstructured documents capture initial requirements before they've been properly analyzed and converted into formal feature specifications. This directory should ideally be empty or contain only in-progress documents awaiting formalization.

## When to Use This Directory

- When receiving initial client requirements
- For brainstorming sessions that generate raw ideas
- When documenting high-level project goals before breaking them down
- For storing reference materials that will inform multiple features

## Processing Workflow

1. **Add** raw requirements or specifications to this directory
2. **Analyze** each section to identify discrete features, issues, or design needs
3. **Create** appropriate structured documents in their respective directories:
   - `notes/features/` for new functionality
   - `notes/issues/` for bugs or technical debt
   - `notes/design_docs/` for implementation approaches
   - `notes/adr/` for architectural decisions
4. **Remove** the processed content from the unstructured document
5. **Reference** the new structured document with a line like:
   ```
   See: notes/features/001_example_feature.md
   ```
6. **Continue** until the entire unstructured document has been processed

## Document Lifecycle

Unstructured requirements follow this lifecycle:

- **Created**: When receiving initial client specifications
- **Processed**: Gradually converted into formal feature documents
- **Completed**: When all sections have been formalized and referenced

## Best Practices

- Process unstructured documents incrementally rather than all at once
- Prioritize sections based on implementation urgency
- Use the reference format consistently to maintain traceability
- Consider adding status metadata to track processing progress
- Reference the decision-making framework in [DECISION_MAKING.md](../guidelines/DECISION_MAKING.md) when determining how to structure requirements

> **Note**: As mentioned in [DECISION_MAKING.md](../guidelines/DECISION_MAKING.md), converting unstructured requirements into formal feature requests should be prioritized to ensure clear implementation guidance.
