---
description: Define the overall writing principles and style guide for the content.
handoffs:
  - label: Build Writing Specification
    agent: writekit.specify
    prompt: Create a detailed writing specification based on the updated writing constitution. I want to write about...
---

## User Input

```text
$ARGUMENTS
```

You **MUST** consider the user input before proceeding (if not empty).

## Outline

You are updating the writing constitution at `/memory/constitution.md`. This file defines the core writing principles and style guide for all content within this project. Your job is to (a) collect/derive concrete values for these principles, (b) fill the template precisely, and (c) propagate any amendments across dependent artifacts.

Follow this execution flow:

1. Load the existing constitution template at `/memory/constitution.md`.
   - Identify every placeholder token of the form `[ALL_CAPS_IDENTIFIER]`.
   **IMPORTANT**: The user might provide specific instructions or examples for the writing principles. Respect these inputs.

2. Collect/derive values for placeholders:
   - If user input (conversation) supplies a value, use it.
   - Otherwise infer from existing repo context (README, prior constitution versions if embedded).
   - For governance dates: `RATIFICATION_DATE` is the original adoption date (if unknown ask or mark TODO), `LAST_AMENDED_DATE` is today if changes are made, otherwise keep previous.
   - `CONSTITUTION_VERSION` must increment according to semantic versioning rules:
     - MAJOR: Backward incompatible principle removals or redefinitions.
     - MINOR: New principle/section added or materially expanded guidance.
     - PATCH: Clarifications, wording, typo fixes, non-semantic refinements.
   - If version bump type ambiguous, propose reasoning before finalizing.

3. Draft the updated constitution content:
   - Replace every placeholder with concrete text (no bracketed tokens left except intentionally retained template slots that the project has chosen not to define yet—explicitly justify any left).
   - Preserve heading hierarchy and comments can be removed once replaced unless they still add clarifying guidance.
   - Ensure each principle section is clear, actionable, and reflects the defined writing style, audience, quality, and ethics.

4. Consistency propagation checklist (convert prior checklist into active validations):
   - Read `/templates/plan-template.md` and ensure any "Constitution Check" or rules align with updated principles.
   - Read `/templates/spec-template.md` (should be renamed to writing-spec-template.md or similar) for scope/requirements alignment—update if constitution adds/removes mandatory sections or constraints.
   - Read `/templates/tasks-template.md` and ensure task categorization reflects new or removed principle-driven task types (e.g., tone review, citation checks).
   - Read each command file in `/templates/commands/*.md` (excluding research.md, write.md which are later stages) to verify no outdated references remain.
   - Read any runtime guidance docs (e.g., `README.md`). Update references to principles changed.

5. Produce a Sync Impact Report (prepend as an HTML comment at top of the constitution file after update):
   - Version change: old → new
   - List of modified principles (old title → new title if renamed)
   - Added sections
   - Removed sections
   - Templates requiring updates (✅ updated / ⚠ pending) with file paths
   - Follow-up TODOs if any placeholders intentionally deferred.

6. Validation before final output:
   - No remaining unexplained bracket tokens.
   - Version line matches report.
   - Dates ISO format YYYY-MM-DD.
   - Principles are declarative, testable, and free of vague language ("should" → replace with MUST/SHOULD rationale where appropriate).

7. Write the completed constitution back to `/memory/constitution.md` (overwrite).

8. Output a final summary to the user with:
   - New version and bump rationale.
   - Any files flagged for manual follow-up.
   - Suggested commit message (e.g., `docs: amend writing constitution to vX.Y.Z (style guide update + ethical guidelines)`).

Formatting & Style Requirements:

- Use Markdown headings exactly as in the template (do not demote/promote levels).
- Wrap long rationale lines to keep readability (<100 chars ideally) but do not hard enforce with awkward breaks.
- Keep a single blank line between sections.
- Avoid trailing whitespace.

If the user supplies partial updates (e.g., only one principle revision), still perform validation and version decision steps.

If critical info missing (e.g., ratification date truly unknown), insert `TODO(<FIELD_NAME>): explanation` and include in the Sync Impact Report under deferred items.

Do not create a new template; always operate on the existing `/memory/constitution.md` file.