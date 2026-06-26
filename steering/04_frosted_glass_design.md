---
title: Premium Frosted Glass UI Design System
inclusion: always
---

# Premium Frosted Glass UI Design System

Enforce the visual aesthetic of clean, premium minimalism with iOS-style frosted glass layouts.

## Visual Language Guidelines
*   **Palette**: Soft, clean light backgrounds (`#FAFAFA` or `#F4F4F6`) with refined indigo primary accents (`#4F46E5`). Avoid pure black, pure red, or raw neon colors.
*   **Glassmorphism**: Use backdrop filters for panels and modals.
    *   Example utility classes: `.glass` (low opacity white with `backdrop-filter: blur(12px)`) and `.glass-strong`.
*   **Typography**: Clean sans-serif headings and body text (Inter, Roboto, or Outfit). No defaults like Times New Roman.
*   **Micro-Animations**: Add subtle rise-and-fade animations (`.rise`) for loaded content and interactive hover scaling for buttons (e.g. `hover:scale-[1.02] active:scale-[0.98]`).
*   **Shadows**: Use native, soft, high-diffusion shadows (e.g. `shadow-sm`, `shadow-md` with custom low opacity black) rather than harsh black borders.
