# Changelog

## 8.0.4 — Initial independent release candidate

- Independent Obsidian plugin ID `notifications-for-tasks` and product name **Notifications for Tasks**.
- Public URI, view type, workspace events, API lookup examples, and local manager cache receive unique names.
- Built-in financial support section and two embedded payment QR images disabled/removed from distributed JavaScript.
- Standalone settings backup identity; no import/migration from Ntfy Notifications.
- Retained legacy internal JavaScript and CSS identifiers for selective upstream patch review.
- Tasks-centered documentation, project credits and independent release history.
- Added category-based control over in-app pop-up messages without disabling ntfy push delivery.
- Added durable recovery for interrupted scans, including retries after read errors and mobile suspension.
- Added optional mobile full verification every 6, 12, 24, or 48 hours (24 hours by default), run only while Obsidian is active and idle.
- Improved deferral of incremental scans while a full scan is already in progress.
- Assigned an independent local device-ID storage key (`notifications-for-tasks-device-id`) to prevent a collision with the original plugin.

This version is based on the provided `1.8.0_RC5` development files. The current update passed JavaScript syntax validation; the updated build still needs in-app regression testing on target devices before directory submission.
