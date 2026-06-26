---
title: Single File First Architecture
inclusion: always
---

# Single File First Architecture

To speed up SaaS prototyping and prevent directory bloat (folder-explosion), prioritize keeping code cohesive and local.

## Rules
1.  **Keep it Local**: When building a new feature, route, or component, start by writing all functions, types, and sub-components inside a **single file** first.
2.  **Delay Extraction**: Do NOT extract code into new files or folders (e.g., `helpers/`, `utils/`, `components/`) until:
    *   The file exceeds 400 lines of code.
    *   **AND** the code is actually imported and reused by at least two other completely unrelated files.
3.  **Co-locate Types**: Keep TypeScript interfaces, Zod schemas, and database helper functions in the file where they are primarily used.
4.  **Inline CSS/Styles**: Use utility classes (like Tailwind) or inline CSS rather than creating new stylesheet files.
