# Notifications for Tasks

[Русский](README.ru.md)

**Notifications for Tasks** is an Obsidian plugin designed to work alongside [Tasks](https://github.com/obsidian-tasks-group/obsidian-tasks). It turns tasks into reminders, sends notifications through ntfy and other channels, automates recurring tasks, and aims to use device resources efficiently.

## Quick start

- Create an account at [ntfy](https://ntfy.sh/app), install the [app](https://play.google.com/store/apps/details?id=io.heckel.ntfy), tap the "+" button in the lower-right corner, and enter a topic name without special characters such as `!@#$%^&` (you can use a password generator). The topic name should be as difficult to guess as a password. Otherwise, someone could accidentally subscribe to your topic and read your notifications. For example: `S8JmCJhn`.
- Open **Notifications for Tasks → Channels → Channels → In use** (expand the section) **→ Topic**, enter the generated topic name and press the test button. Enter just the name (`S8JmCJhn`), not a URL (`ntfy.sh/S8JmCJhn`). You should receive a notification on your phone.
- To receive notifications, tasks need to use this format: `Test 11:00 🔁 every 6 days 🏁 delete 📅 2026-10-17`. In other words: **task text → time → Tasks metadata**.

If you put the time in the middle of, or after, the Tasks metadata, this is an error. It can break the task, prevent a notification, and make the task invisible to the Tasks plugin.

Please read the following sections to become familiar with the plugin.

## Main features

### 1. ntfy notifications even when Obsidian is closed

The plugin can send scheduled notifications to the ntfy server in advance. Once a notification has been scheduled successfully, Obsidian can be closed and the message will arrive at the appointed time.

If a task is postponed, completed, or deleted, the plugin can update or cancel its previously scheduled notification. Advance reminders, repeated notifications, and separate rules for tasks without a specified time are also available.

**Important:** The ntfy server limits how far ahead messages may be scheduled. More distant reminders may remain in the local queue until Obsidian starts or scans again. Jobs already submitted to the server and those still in the local queue behave differently.

### 2. Automatically completing tasks through Tasks

Imagine wanting a recurring reminder without having to open Obsidian every time just to mark the task as completed.

Add the `#autodone` tag (or another tag configured in settings). Once the task's scheduled time arrives, the plugin can automatically complete it through Tasks, preserving Tasks' recurring-task logic.

If Obsidian is closed, the change is made the next time the app starts.

Custom status sequences are supported:

- `[ ] → [x]` — one toggle.
- `[ ] → [/] → [x]` — two toggles.

Under **Automation → Maximum Tasks status toggles**, you can set the maximum number of toggles needed to complete a task. The plugin uses the Tasks mechanism rather than simply replacing characters in Markdown.

### 3. Selective scanning, filters, and quiet hours

You do not have to scan the entire vault. You can select only the Markdown files and folders you need, such as `Habits`, `Projects/Work`, or a particular daily note.

If the list is empty, the entire vault is scanned.

You can also filter tasks by tags: for example, send notifications only for `#reminder`, while excluding tasks marked `#no-reminder`.

Quiet hours help limit notifications at unwanted times.

### 4. Reminder manager and Why not diagnostics

The built-in manager (the bell icon in the sidebar) lets you:

- View upcoming notifications and their states.
- Open the source notes, change the time, and complete tasks through Tasks.
- Manage individual reminders.
- Find out why a task did not receive a notification.

The last feature is available in **Why not**. The plugin examines task format, time, filters, and other conditions, and explains the reason for the problem. Certain misplaced-time errors can also be fixed automatically.

### 5. Resource efficiency on phones and computers

I often use Obsidian on my phone, so fast startup and low background resource use matter a great deal to me.

The plugin supports **Mobile** and **Desktop** profiles, which organize scanning and change processing differently.

The mobile profile focuses on resource efficiency, while the desktop profile allows more active checks. Both respect the files and folders selected by the user.

### 6. English interface and external translations

The main interface language is English. Separate JSON translation files are supported for other languages, including Simplified Chinese, Spanish, Hindi, Bengali, Portuguese, Russian, and Japanese.

For example, `ru_8.0.4.json` is a Russian translation prepared for version `8.0.4`.

Future plugin updates can continue using this file. New or untranslated interface elements remain in English until the translation is updated.

**To install a language file**, place it in:

`.obsidian/plugins/notifications-for-tasks/locales/`

Then reload the language packs in the plugin settings.

Translations are distributed separately to keep the main plugin code simpler. Availability depends on the language files that have been published.

### 7. Multiple notification channels

The primary focus is **ntfy**, because it can schedule messages on the server in advance and deliver them while Obsidian is closed.

Telegram, Discord, Slack, Matrix, Feishu, WeCom, QQ Bot, email through an HTTP gateway, and generic Webhooks are also supported.

Unlike delayed ntfy notifications, sending through Telegram in the current implementation requires Obsidian to be running when the message is transmitted.

## Important notes

For full automation, recurring-task handling, and custom status support, installing and enabling **Tasks** is recommended.

Notifications already accepted by the ntfy server can arrive while Obsidian is closed. However, processing changes to notes, scheduling subsequent notifications, and automatically completing tasks require Obsidian to run.

If you use [Lazy Loader](https://github.com/alangrainger/obsidian-lazy-plugins), make sure the Tasks plugin finishes loading before Notifications for Tasks starts; this is necessary for correct operation.

## Project history

I originally used [Ntfy Notifications](https://github.com/arias007/obsidian-ntfy) by **Murat (@arias007)**.

I was missing one feature, so I added it myself. At first, I only wanted to send the improved build to the original author, but new ideas, fixes, and features gradually followed.

Eventually, the modification diverged significantly from the original. The author offered to collaborate, but I decided to develop the project independently, focusing on my own priorities: **Tasks, ntfy, task automation, and mobile resource efficiency**.

That is how Notifications for Tasks came to be.

This is an independent project developed and maintained by **Alekcei-BAV**, based on Murat's original work.

Thank you to the original author for his work and for granting [permission](https://github.com/arias007/obsidian-ntfy/issues/2) to create the modification.

**License:** MIT, with the original developer's copyright notices preserved.
