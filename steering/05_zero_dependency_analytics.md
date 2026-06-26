---
title: Zero-Dependency In-App Analytics
inclusion: always
---

# Zero-Dependency In-App Analytics

Avoid importing heavy, cookie-consent-requiring third-party analytics libraries (Google Analytics, Mixpanel, etc.) for basic traffic and purchase metrics.

## Rules
1.  **Database-Backed Event Logs**: Store page views, checkout clicks, and payment success events in a simple, lightweight PostgreSQL table (e.g., `events` or `settings` updates).
2.  **Simple Columns**:
    *   `id` (serial/bigint)
    *   `name` (text, e.g. "page_view_home", "checkout_click")
    *   `metadata` (jsonb for flexibility, e.g., browser agent, referral source)
    *   `createdAt` (timestamp)
3.  **Low Impact**: Insert event rows asynchronously or at the end of request handlers to avoid slowing down user operations.
4.  **No Tracking Cookies**: Prioritize server-side analytics (IP hash or referrer headers) over setting tracking cookies, making your SaaS compliant with GDPR/CCPA out-of-the-box.
