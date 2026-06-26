---
title: SQLite to PostgreSQL Migration Strategy
inclusion: always
---

# SQLite to PostgreSQL Migration Strategy

Guidelines for migrating local SQLite databases to production PostgreSQL instances in Node.js/Bun codebases.

## Rules
1.  **Map Data Types Accurately**:
    *   Map `INTEGER` (SQLite) -> `integer` or `bigint` (Postgres). Note: Telegram IDs exceed 32-bit integers, so always map them to `bigint` in PostgreSQL (with `{ mode: "number" }` in Drizzle).
    *   Map `TEXT` (SQLite) -> `text` (Postgres).
    *   Map timestamps from numeric integers (Unix epoch in SQLite) -> standard `timestamp` or `timestamp(withTimezone)` in Postgres.
2.  **Handle Serial Key Resets**: When seeding or copying data from SQLite to Postgres, ensure the serial primary key sequences are updated to match the maximum ID (e.g. using `SELECT setval('table_id_seq', COALESCE((SELECT MAX(id)+1 FROM table), 1), false)`).
3.  **Replace SQLite Pragmas**: Remove any SQLite-specific directives (like `PRAGMA foreign_keys = ON` or `PRAGMA journal_mode`) and replace them with standard PostgreSQL configurations.
4.  **Transaction Blocks**: Execute batch migrations within a single database transaction (`BEGIN; ... COMMIT;`) to ensure atomicity. If a single copy operation fails, roll back everything.
