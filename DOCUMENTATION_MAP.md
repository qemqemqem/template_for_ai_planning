# Documentation Map

This project uses a structured documentation system to guide development. This map shows how different document types relate to each other in the development workflow.

## Document Flow Diagram

```
Unstructured Requirements
        ↓
    Features
    ↙     ↘
Issues    Design Docs
    ↘     ↙
   Implementation
    ↙     ↘
 ADRs     Knowledge
```

## Document Relationships

- **Unstructured Requirements** → **Features**: Requirements are formalized into specific feature requests
- **Features** → **Design Docs**: Complex features require design documentation before implementation
- **Features** → **Issues**: Features may identify bugs or refactoring needs
- **Design Docs** → **Implementation**: Design documents guide the implementation process
- **Implementation** → **ADRs**: Implementation may require architectural decisions
- **Implementation** → **Knowledge**: Implementation discoveries are documented as knowledge

## Document Lifecycle

Each document type follows its own lifecycle, which is detailed in its respective documentation:
- Unstructured Requirements: See [PLANNING.md](notes/unstructured/PLANNING.md)
- Features: See [FEATURES.md](notes/features/FEATURES.md)
- Design Documents: See [DESIGN_DOCS.md](notes/design_docs/DESIGN_DOCS.md)
- Architecture Decision Records: See [ADR.md](notes/adr/ADR.md)
- Knowledge Documents: See [KNOWLEDGE.md](notes/knowledge/KNOWLEDGE.md)

## Cross-Referencing Convention

Documents should reference each other using the following format:
- Features: `[feature-NNN]` (e.g., `[feature-001]`)
- Issues: `[issue-NNN]` (e.g., `[issue-002]`)
- Design Docs: `[design-NNN]` (e.g., `[design-003]`)
- ADRs: `[adr-NNN]` (e.g., `[adr-004]`)
- Knowledge: `[knowledge-NNN]` (e.g., `[knowledge-005]`)

Include these references in:
- YAML frontmatter under `related_docs`
- Document text when discussing related content
- Code comments when implementing related functionality
- Commit messages when changes relate to specific documents
