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
        ↓
     ADRs
        ↓
   Knowledge
```

## Document Relationships

- **Unstructured Requirements** → **Features**: Requirements are formalized into specific feature requests
- **Features** → **Design Docs**: Complex features require design documentation before implementation
- **Features** → **Issues**: Features may identify bugs or refactoring needs
- **Design Docs** → **Implementation**: Design documents guide the implementation process
- **Implementation** → **ADRs**: Implementation may require architectural decisions
- **Implementation** → **Knowledge**: Implementation discoveries are documented as knowledge

## Document Lifecycle

### Unstructured Requirements
- **Created**: When receiving initial client specifications
- **Processed**: Gradually converted into formal feature documents
- **Completed**: When all sections have been formalized and referenced

### Features
- **Proposed**: Initial feature specification
- **Approved**: Accepted for implementation
- **In-Progress**: Currently being implemented
- **Completed**: Implementation finished and verified
- **Deprecated**: No longer supported or relevant

### Design Documents
- **Draft**: Initial design proposal
- **In-Review**: Under consideration and feedback
- **Approved**: Accepted for implementation
- **Implemented**: Design has been realized in code
- **Deprecated**: Design is no longer relevant

### Architecture Decision Records
- **Proposed**: Initial decision proposal
- **Accepted**: Decision has been accepted
- **Rejected**: Decision was considered but not accepted
- **Deprecated**: Decision is no longer valid
- **Superseded**: Decision has been replaced by a newer one

### Knowledge Documents
- **Created**: Initial documentation of insight
- **Verified**: Insight has been confirmed
- **Updated**: Additional information added
- **Archived**: No longer actively referenced but kept for historical value

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
