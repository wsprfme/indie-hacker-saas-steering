# Kiro & Agentic AI Global Steering Files

This repository contains global steering files and rules for agentic development platforms (such as Kiro and Gemini Antigravity). These rules help guide the AI agent's behavior to follow specific development paradigms, conform to environment-specific shells, utilize optimal search routes, and notify the developer on long-running tasks.

## Contents
*   **`steering/ponytail.md`**: Enforces minimal, standard-library-first, and over-engineering-free coding practices (adapted from `DietrichGebert/ponytail`).
*   **`steering/system_info.md`**: Declares OS-specific details (Windows Server, PowerShell 5.1, installed/unavailable tools) to prevent incorrect shell execution.
*   **`steering/library_research.md`**: Defines optimal library documentation search strategies using `context7` MCP and fallback web search.
*   **`steering/telegram_notifications.md`**: Establishes a protocol for sending completion alerts to the developer via a Telegram bot for long-running processes.

## Usage
To use these files in Kiro globally, clone this repository or copy the contents of the `steering/` folder into your global Kiro steering directory:
*   **Windows**: `C:\Users\<Username>\.kiro\steering\`
*   **macOS/Linux**: `~/.kiro/steering/`
