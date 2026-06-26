---
title: Lightweight Telegram Long-Polling Bot
inclusion: always
---

# Lightweight Telegram Long-Polling Bot

Best practices for managing long-polling Grammy bots in a serverless-adjacent or resource-constrained environment.

## Rules
1.  **Long Polling Over Webhooks**: For simple deployments and local development, prioritize long polling using `@grammyjs/runner` or `bot.start()` over webhooks. This avoids the need for exposing ports, reverse proxies, and setting up SSL certificates on origin.
2.  **Graceful Shutdown**: Implement listeners for `SIGINT` and `SIGTERM` to stop the bot runner gracefully before the Node/Bun process terminates:
    *   Example: `process.once('SIGINT', () => bot.stop())`.
3.  **Command Validation**: Check that commands (`/start`, `/claim`, `/menu`) are handled using grammY's specific command middleware (`bot.command(...)`) rather than parsing raw text inside generic message listeners.
4.  **Admin Broadcast Safety**: When broadcasting messages to multiple Telegram users, handle individual block errors (`Forbidden: bot was blocked by the user`) in a try-catch to prevent a single blocked user from terminating the entire broadcast loop.
5.  **State Management**: Store session state (e.g. pending orders, OTP state) in your PostgreSQL database rather than in-memory variables. This ensures the bot state survives server restarts and Scheduled Task restarts.
