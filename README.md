# Indie Hacker SaaS Speedrun & Rapid Prototyping Steering Rules

This repository contains a curated set of **10 global steering files** designed for AI coding assistants (such as Kiro and other agentic IDEs). These files enforce minimal, robust, and highly-efficient development practices optimized for indie hackers building and deploying SaaS applications rapidly.

## 📋 The 10 Steering Files
All files are located in the `steering/` directory:

1.  **`01_ponytail_lazy_dev.md`**: Enforces minimal, standard-library-first, and over-engineering-free coding practices (YAGNI).
2.  **`02_single_file_first.md`**: Prevents folder-explosion by keeping features, types, and components in a single file until extraction is strictly necessary.
3.  **`03_postgres_drizzle_optimization.md`**: Best practices for PostgreSQL database operations, Drizzle ORM schemas, and race-condition prevention (row-level locking).
4.  **`04_frosted_glass_design.md`**: Guidelines for implementing a clean, premium, iOS-style frosted glass UI using a light palette, indigo accents, and micro-animations.
5.  **`05_zero_dependency_analytics.md`**: How to set up simple, GDPR-compliant server-side event tracking without third-party tracking scripts.
6.  **`06_seo_metadata_practices.md`**: Ensures automatic search engine optimization, meta descriptions, and Twitter/Open Graph card configurations on every page.
7.  **`07_sqlite_to_postgres_migration.md`**: Strategies for migrating data types, sequence keys, and transactions from local SQLite databases to production PostgreSQL.
8.  **`08_error_boundaries_data_loss.md`**: Strict input validation (e.g., Zod), error boundaries, and idempotent mutations to ensure data integrity.
9.  **`09_whatsapp_evolution_integration.md`**: Best practices for sending alerts and credentials via the Evolution WhatsApp API safely and reliably.
10. **`10_telegram_polling_bot.md`**: Rules for building lightweight long-polling Telegram bots (using Grammy) with persistent states and robust exception handling.

## 🚀 Usage in Kiro
To use these steering files globally, copy the contents of the `steering/` folder into your global Kiro steering directory:
*   **Windows**: `C:\Users\<Username>\.kiro\steering\`
*   **macOS/Linux**: `~/.kiro/steering/`
