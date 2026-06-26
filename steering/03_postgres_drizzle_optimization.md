---
title: PostgreSQL & Drizzle ORM Optimization
inclusion: always
---

# PostgreSQL & Drizzle ORM Optimization

Maximize performance and robustness when interfacing with PostgreSQL using Drizzle ORM.

## Rules
1.  **Drizzle-Kit Push**: For rapid database schema changes, prioritize `drizzle-kit push` (or `db:push`) to sync schemas immediately without writing verbose migration SQL scripts, unless deploying to a critical production database.
2.  **Explicit Indexes**: Always index foreign keys and columns that are frequently used in `WHERE`, `ORDER BY`, or `JOIN` clauses (e.g., `status`, `userId`, `claimKey`).
3.  **Prevent Race Conditions (Row Locks)**:
    *   For inventory checkout, stock reservation, or balance deduction, always use row-level locking (`SELECT ... FOR UPDATE` or Drizzle's `.for("update")`) inside a database transaction to prevent double-spending or overselling.
4.  **Avoid Joins for Simple Fetch**: If fetching a record and its direct relation, check if two fast sequential queries are simpler and cleaner than a complex SQL join.
5.  **Use Connection Pools**: Ensure the postgres client utilizes connection pooling to prevent opening/closing TCP connections on every API request.
