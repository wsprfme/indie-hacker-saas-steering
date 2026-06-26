---
title: Trust Boundaries & Data-Loss Prevention
inclusion: always
---

# Trust Boundaries & Data-Loss Prevention

Ensure the codebase remains "lazy but not negligent" by enforcing strict validation at input boundaries and preventing database corruption.

## Rules
1.  **Zod Schema Validation**: Validate all incoming payloads (from web API routes, Telegram bot commands, or webhook bodies) using strict Zod schemas before executing database mutations or business logic.
2.  **Explicit Try-Catches**: Wrap all external integration calls (Telegram API, WhatsApp Evolution API, Payment Gateway requests) in individual try-catch blocks. If one external call fails, it must NOT crash the entire app process.
3.  **Idempotent Mutations**: Design payment webhook handlers and order completion functions to be fully **idempotent**. Multiple identical requests (e.g. repeated payment notifications) must not result in duplicate order fulfillments or stock decreases.
4.  **Graceful Recovery**: In the event of a database query failure during checkout, release any atomic locks or stock reservations immediately to prevent locking resources indefinitely.
