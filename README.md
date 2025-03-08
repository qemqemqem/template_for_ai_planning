# AI Planning Template

A structured documentation system designed to help AI assistants plan, track, and implement software projects effectively.

## Overview

This template provides a comprehensive framework for AI-assisted development with a focus on:

- Structured decision-making based on task complexity
- Clear documentation paths for different types of work
- Systematic tracking of progress and checkpoints
- Conversion of unstructured requirements into actionable tasks

## Directory Structure

- `/guidelines/` - Standards and decision frameworks
- `/notes/` - Documentation organized by purpose:
  - `adr/` - Architecture Decision Records
  - `design_docs/` - Implementation plans for complex features
  - `features/` - Feature specifications
  - `issues/` - Bug reports and refactoring needs
  - `knowledge/` - Accumulated insights and patterns
  - `unstructured/` - Raw requirements awaiting formalization
  - `working/` - Active tracking documents

## Getting Started

1. Fork this template and rename it for your project
2. Place client specifications in `notes/unstructured/`
3. Run aider with `aider --load .instructions`
4. Work with the AI to:
   - Convert unstructured requirements into formal feature documents
   - Create appropriate design documents for complex features
   - Implement features according to the decision-making framework
   - Document architectural decisions and accumulated knowledge

## Documentation Workflow

The documentation system follows a structured flow:

1. **Unstructured Requirements** → Client specifications are placed in `notes/unstructured/`
2. **Formalization** → Requirements are converted into feature documents in `notes/features/`
3. **Design** → Complex features (SP5+) require design documents in `notes/design_docs/`
4. **Implementation** → Code is written following the decision-making framework
5. **Knowledge Capture** → Insights and patterns are documented in `notes/knowledge/`
6. **Architecture Decisions** → Significant architectural choices are recorded in `notes/adr/`

## Philosophy

This template embodies a "plan first, code second" approach that leverages AI assistance while maintaining human oversight. By structuring the development process through documentation, both the AI assistant and human developers maintain a clear understanding of project goals, decisions, and progress.
