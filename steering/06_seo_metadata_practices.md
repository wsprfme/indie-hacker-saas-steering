---
title: Automated SEO & Metadata Practices
inclusion: always
---

# Automated SEO & Metadata Practices

Ensure every page on the web app is automatically optimized for search engines (Google, Bing) and social sharing (Twitter, Open Graph) from the very first commit.

## Rules
1.  **Single H1 Tag**: Every web page MUST have exactly one `<h1>` tag containing the primary topic/title of the page.
2.  **Semantic HTML**: Structure layouts with proper HTML5 landmark elements: `<header>`, `<main>`, `<nav>`, `<footer>`, `<section>`.
3.  **Metadata Fields**: Automatically declare:
    *   `<title>`: Structured as `[Page Name] | [Brand Name]` (under 60 characters).
    *   `<meta name="description">`: Compelling summary under 160 characters.
    *   `<meta property="og:image">` & `<meta name="twitter:image">`: Absolute path to a high-quality preview image (e.g., banner URL).
4.  **Descriptive Alt Texts**: Every `<img>` tag must include a descriptive `alt` attribute. Avoid generic names like "image" or "icon".
5.  **Unique IDs for Testing**: Assign unique, descriptive `id` attributes to all buttons, links, inputs, and interactive panels to enable browser automated testing.
