# Changelogs

All notable changes to the Spam Sharer project will be documented in this file.

## Version: 2.0
Since: July 21, 2025

- Added internet connection detection in `update.py` using the `requests` library to check connectivity to `https://www.google.com` with a 5-second timeout.
- Implemented handling for no internet connection, displaying a yellow panel.
- Enhanced error handling in `check_internet_connection` to catch `requests.exceptions.RequestException`, including timeout errors (e.g., `HTTPSConnectionPool... Read timed out`), ensuring consistent no-internet messaging.
- Added logging of internet check failures, including timeout errors, to `update_log.txt` for debugging and tracking.
- Ensured seamless return to the main menu after no-internet prompts using `main_instance.show_menu()` when available, with fallback for standalone execution.

## Version: 1.9
Since: July 19, 2025

- Fixed incorrect batch counting in resume logic to prevent batch numbers exceeding total batches (e.g., `Batch 66/60`), ensuring `total_batch` is calculated as `ceil(total_shares / shares_per_delay)`.
- Improved resume data validation in `_load_resume_data` to cap `successful_batch` at `ceil(successful_shares / shares_per_delay)` and recalculate `total_batch` for consistency.
- Updated batch tracking in `main_sharing` to increment `current_batch` after successful batch completion, ensuring accurate display (e.g., `Batch 64/100`).
- Enhanced configuration summary to reflect correct `total_batch` and estimated time based on remaining batches (`total_batch - successful_batch`).
- Improved reliability of progress saving by ensuring `successful_batch` and `total_batch` are consistently updated in `resume.json` during interruptions or restrictions.
- Fixed the MarkupError regarding the closing tag in the `spam_detected`.

## Version: 1.8
Since: July 18, 2025

- Enhanced resume data structure to include `total_batch` and `successful_batch` for precise batch tracking, and renamed `count` to `total_shares` for clarity in resume JSON files.
- Improved progress saving to occur after every successful batch, before delays, on spam restriction detection, and on process termination (SIGTERM/SIGINT) to minimize data loss.
- Added signal handling for SIGTERM and SIGINT to save progress when Termux is killed by Android or interrupted by Ctrl+C, ensuring reliable recovery.
- Updated resume logic to use `successful_batch` and `successful_shares` for accurate resumption, respecting `min_delay`, `max_delay`, and `shares_per_delay` from the resume file.
- Added backward compatibility for old resume files by converting `count` to `total_shares` during loading.
- Updated configuration summary and result panels to display `successful_batch` alongside `successful_shares` for better progress visibility.

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
