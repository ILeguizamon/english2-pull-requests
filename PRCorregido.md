## Context
This PR addresses issue #102, which highlighted the need for users to receive feedback after sample validation.
It builds on pull request #78, which implemented the sample validation workflow.
FYI: before this update, users had to check manually, causing delays and confusion.

## Changes
- Added `NotificationService` in the backend to handle alerts.
- Created `ValidationNotification` React component to show messages on the user dashboard.
- Updated `/notifications` endpoint for fetching user alerts.
- Updated database schema with `user_notifications` table (fields: `user_id`, `sample_id`, `status`, `read_at`).
- Minor refactor in validation controller for reuse.
- Documentation updated in `/docs/notifications.md`.
- OOTB: works for most validation scenarios. TBD: email and push notifications in next phase.

## Impact
- Users receive real-time feedback, improving experience and reducing support requests.
- The system is scalable for future notification types (email, push).
- ETA for full integration: next sprint.

## Review Focus
Please review:
- The logic connecting validation and notification creation.
- The UI component design (`ValidationNotification`).
- Database migration for the new notifications table.

ICYMI: updated documentation is in `/docs/notifications.md`.

## Collaborators
IMO, the notification feature looks solid. Thanks to @RickQA and @lucasRZ for the feedback and support during testing and code review!

✅ **Status:** Ready for review  
🚀 **Merge planned:** EOD tomorrow