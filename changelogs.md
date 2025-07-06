# Changelog

All notable changes to the Spam Sharer project will be documented in this file.

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

- Added advanced user-agent rotation using `fake-useragent` for stealthy operation on Meta platforms.
- Added seamless account management to add, switch, or manage multiple accounts, with clipboard support (requires Termux:API).
- Added support for flexible account input via cookie strings and appstate JSON imports.
- Added support for multiple URL types, including video links and group posts, for versatile sharing.
- Added core spam sharing functionality with fixed delay and progress tracking.
