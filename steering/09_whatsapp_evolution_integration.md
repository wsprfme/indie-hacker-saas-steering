---
title: WhatsApp Evolution API Integration
inclusion: always
---

# WhatsApp Evolution API Integration

Guidelines for building lightweight, robust notifications using the Evolution API for WhatsApp.

## Rules
1.  **Strict Rate-Limiting**: To prevent WhatsApp number bans, do not send bulk messages simultaneously. Queue messages and implement a delay of 2 to 5 seconds between sequential messages.
2.  **Verify Connection Status**: Prior to sending a notification, query the Evolution API session status `/instance/connectionStatus`. If the status is not connected, fallback to sending an alert to the admin via Telegram.
3.  **Sanitize Phone Numbers**: Normalize receiver numbers to E.164 format (digits only, including country code, e.g., `628123456789`). Strip any symbols like spaces, dashes, or the leading `+` before sending the request.
4.  **Simple Payloads**: Keep message payloads as plain text. Avoid complex markdown formats which WhatsApp might render incorrectly.
