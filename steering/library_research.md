---
title: Library Research and Documentation Strategy
inclusion: always
---

# Library Research and Documentation Strategy

This steering file defines the mandatory protocol for searching library documentation and researching development tech stacks.

## 1. Searching for Library Documentation
When looking up library documentation, APIs, types, or syntax for the latest/latest versions, the AI agent MUST follow this exact sequence:
1.  **Primary Tool: MCP context7**:
    *   First, use the `context7` MCP server tools (`resolve-library-id` and `query-docs`) to locate and query official documentation.
2.  **Fallback: Web Search / Browsing**:
    *   If the required library or documentation is not found in `context7`, the agent MUST fallback to searching the web/internet (e.g. using web search/browsing tools) to find the latest documentation.

## 2. Tech Stack Research Before Development
Before implementing any development task, the agent MUST:
*   Perform initial internet research to gather the latest details, best practices, and version info for the chosen tech stack.
*   Avoid making assumptions based solely on static knowledge. Ensure the proposed architecture aligns with current official recommendations.
