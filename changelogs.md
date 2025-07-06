# Changelog

All notable changes to the Facebook MonoToolkit project will be documented in this file.

## [1.5] - 2025-07-07

- Added network error handling with pause-and-resume functionality for connectivity issues.
- Added spam restriction detection to stop sharing and suggest account switching with recovery time.
- Added masked post link display in configuration panel for improved readability.
- Added total network issues count to results panel for better process transparency.
- Improved configuration panel with line break before post link for clarity.
- Improved delay message to use console output with cyan-colored delay time instead of panel.
- Fixed minor bugs and improved error messaging for network and spam restrictions.

## [1.0] - 2025-07-02

- Added advanced user-agent rotation using `fake-useragent` for stealthy operation on Meta platforms.
- Added seamless account management to add, switch, or manage multiple accounts, with clipboard support (requires Termux:API).
- Added support for flexible account input via cookie strings and appstate JSON imports.
- Added support for multiple URL types, including video links and group posts, for versatile sharing.
- Initial release with core spam sharing functionality and progress tracking.
