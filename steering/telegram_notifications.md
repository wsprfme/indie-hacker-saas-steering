---
title: Long-Running Task Telegram Notifications
inclusion: always
---

# Long-Running Task Telegram Notifications

This steering file defines the mandatory protocol for sending Telegram notifications to the user when they leave their PC during long-running tasks.

## Trigger Conditions
The AI agent MUST send a Telegram notification if:
1.  The agent is executing a long-running process (e.g., building features, installing software, running migrations, executing tests, or doing extensive research).
2.  **AND** the user indicates they are leaving their PC (e.g., saying they are going away, going to sleep, scrolling TikTok, going to the restroom, etc.).

## Telegram Bot Credentials
*   **Bot Token**: `YOUR_TELEGRAM_BOT_TOKEN_HERE`
*   **Target Chat ID**: `YOUR_TELEGRAM_CHAT_ID_HERE`

## Action & Message Format Protocol
1.  When the long-running task completes (either successfully or with errors), the agent MUST immediately send a notification message to the user's Telegram.
2.  **Required Message Details**:
    The notification message MUST include:
    *   **Sender Identity**: Explicitly state who is sending the notification (e.g., "Kiro AI Agent").
    *   **Task Details**: A clear description of the task that was executed and its final status (e.g., "Task: PostgreSQL 17 Installation - Success/Failed").
3.  **Notification Method**:
    *   Perform an HTTP GET/POST request to the Telegram Bot API:
        `https://api.telegram.org/botYOUR_TELEGRAM_BOT_TOKEN_HERE/sendMessage`
        with parameters:
        *   `chat_id`: `YOUR_TELEGRAM_CHAT_ID_HERE`
        *   `text`: The formatted status message (URL encoded).
