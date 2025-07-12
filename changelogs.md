# Changelog

All notable changes to the Spam Sharer project will be documented in this file.

## Version: 1.7
Since: July 12, 2025

- Added resume functionality to save progress when interrupted by Ctrl+C or spam restriction detection, storing data in `storage/data/spam_sharing/resume/{content_type}_{content_id}.json`.
- Added support for resuming interrupted posts or videos with a prompt to continue or start fresh.
- Added automatic deletion of resume file upon successful completion to prevent false resume prompts.
- Added support for both post and video URLs with specific resume file naming (`post_<id>.json` or `video_<id>.json`).
- Updated resume prompt styling to match "Enter your link" prompt, removing panel wrapper and redundant (Y/N) input.
- Improved interruption handling to save progress for both user-initiated (Ctrl+C) and spam restriction interruptions with consistent messaging.

## Version: 1.5
Since: July 07, 2025

- Added network error handling with pause-and-resume functionality for connectivity issues.
- Added spam restriction detection to stop sharing and suggest account switching with recovery time.
- Added masked post link display in configuration panel for improved readability.
- Added total network issues count to results panel for better process transparency.
- Added batch processing with configurable shares per batch and random delay ranges.
- Improved configuration panel with line break before post link and batch-based settings.
- Improved delay message to use console output with cyan-colored delay time instead of panel.
- Improved results panel with detailed metrics (batches completed, total time, success rate).
- Fixed minor bugs and enhanced error messaging for network and spam restrictions.

## Version: 1.0
Since: July 03, 2025

- Added advanced user-agent rotation using `fake-useragent` for stealthy operation.
- Added seamless account management to add, switch, or manage multiple accounts, with clipboard support (requires Termux:API).
- Added support for flexible account input via cookie strings and appstate JSON imports.
- Added support for multiple URL types, including video links and group posts, for versatile sharing.
- Added core spam sharing functionality with fixed delay and progress tracking.
