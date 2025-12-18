---
description: Design how to write the content, including its structure, expression techniques, and media elements.
handoffs:
  - label: Conduct Research
    agent: writekit.research
    prompt: Conduct research based on the writing plan, focusing on gathering supporting evidence for key arguments.
---

## User Input

```text
$ARGUMENTS
```

You **MUST** consider the user input before proceeding (if not empty).

## Outline

You are creating a detailed writing plan for a new content piece at `/specs/[FEATURE_NUMBER]-[CONTENT_SLUG]/plan.md`. This plan will outline the content's structure, section details, expression techniques, and planned media elements, building upon the writing specification.

Follow this execution flow:

1.  **Load Writing Specification**: Load the existing writing specification from `/specs/[FEATURE_NUMBER]-[CONTENT_SLUG]/spec.md`. Understand the theme, purpose, audience, and key arguments.
2.  **Extract Core Elements from User Input**: Identify any specific instructions or preferences provided in $ARGUMENTS for the content structure, style, or media.
3.  **Draft the Plan Content**: Based on the writing specification and user input, generate the detailed plan.
    *   `[CONTENT_STRUCTURE]`: Define the hierarchical structure (e.g., introduction, main sections with headings, conclusion).
    *   `[SECTION_ROLES_AND_ALLOCATION]`: Assign a purpose and estimated word count/length to each section.
    *   `[EXPRESSION_TECHNIQUES]`: Suggest rhetorical devices, examples, analogies, or storytelling approaches.
    *   `[REFERENCE_SOURCES]`: Propose types of information sources to be used (e.g., academic papers, industry reports, personal anecdotes).
    *   `[OUTPUT_FORMAT_OPTIMIZATION]`: Tailor the plan for the specified output format (e.g., SEO for blog, chapter flow for book).
    *   `[MEDIA_ELEMENTS_PLAN]`: Outline where images, diagrams, code snippets, or video links will be placed and their purpose.

4.  **Validate against Writing Constitution and Specification**:
    *   Ensure the plan adheres to the principles in `/memory/constitution.md`.
    *   Confirm that the plan fully addresses all requirements in `/specs/[FEATURE_NUMBER]-[CONTENT_SLUG]/spec.md`.

5.  **Output**: Write the completed plan to `/specs/[FEATURE_NUMBER]-[CONTENT_SLUG]/plan.md`.

## Output Format:

Please use the following Markdown structure for the `plan.md` file. Replace all bracketed placeholders `[ALL_CAPS]` with concrete information.

```markdown
# Writing Plan: [CONTENT_THEME]

## 1. Overview

This document outlines the detailed plan for writing the content piece "[CONTENT_THEME]", based on its specification. It covers the structure, style, and media elements.

## 2. Content Structure

### Main Sections
[CONTENT_STRUCTURE] (e.g.,
-   **Introduction**: (500 words) Hook, thesis statement.
-   **Chapter 1: Foundations**: (1500 words) Key concepts, definitions.
    -   Subsection 1.1: Historical Context (500 words)
    -   Subsection 1.2: Core Principles (1000 words)
-   **Chapter 2: Application**: (2000 words) Practical examples, use cases.
    -   Subsection 2.1: Case Study A (1000 words)
    -   Subsection 2.2: Case Study B (1000 words)
-   **Conclusion**: (500 words) Summary, future outlook, call to action.
]

## 3. Section Roles and Allocation

| Section         | Role                                      | Estimated Length | Key Points to Cover                                              |
|-----------------|-------------------------------------------|------------------|------------------------------------------------------------------|
| Introduction    | Grab attention, set context               | [LENGTH]         | [KEY_POINTS]                                                     |
| [Section Name]  | [ROLE]                                    | [LENGTH]         | [KEY_POINTS]                                                     |
| ...             | ...                                       | ...              | ...                                                              |
| Conclusion      | Summarize, provide final thoughts         | [LENGTH]         | [KEY_POINTS]                                                     |

## 4. Expression Techniques

[EXPRESSION_TECHNIQUES] (e.g.,
-   Use analogies to explain complex concepts.
-   Incorporate storytelling elements in case studies.
-   Employ a persuasive tone when discussing benefits.
-   Use bullet points for readability.
]

## 5. Media Elements Plan

| Element Type     | Description                               | Placement         | Purpose                                     |
|------------------|-------------------------------------------|-------------------|---------------------------------------------|
| Image/Diagram    | [DESCRIPTION]                             | [SECTION/CONTEXT] | [PURPOSE]                                   |
| Code Snippet     | [DESCRIPTION]                             | [SECTION/CONTEXT] | [PURPOSE]                                   |
| Video Link       | [DESCRIPTION]                             | [SECTION/CONTEXT] | [PURPOSE]                                   |

## 6. Reference Source Strategy

[REFERENCE_SOURCES] (e.g.,
-   Primary research papers for scientific claims.
-   Industry reports for market data.
-   Established textbooks for foundational knowledge.
-   Personal interviews for expert opinions.
]

## 7. Output Format Optimization

Considerations for [OUTPUT_FORMAT_OPTIMIZATION] (e.g.,
-   SEO optimization for blog posts (keywords, meta descriptions).
-   Chapter consistency for books (cross-references, index terms).
-   Readability for technical documentation (glossary, clear headings).
]

---

**Generated by Spec Writing Kit CLI**
**Version**: [PLAN_VERSION]
**Date**: [GENERATION_DATE]
```