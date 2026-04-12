# Changelog

This changelog now keeps only the main product milestones.
Small fixes, UI polish passes, and short-lived intermediate steps are intentionally omitted.

## 1.51.0 - Build 1051

- Added an integrated startup guide directly inside the monitor window, rendered on the modern GPU overlay path.
- The guide now highlights the main controls step by step and can be relaunched from `Settings > General`.

## 1.50.0 - Build 1050

- Removed the active legacy fallback path for `Settings`: the application now always opens the modern custom Settings window instead of switching between two runtime implementations.
- Clarified the startup wording around the signal-wait option so it now states the actual behavior more clearly: if waiting for signal is disabled while Windows startup is enabled, the monitor opens directly at logon.

## 1.49.0 - Build 1049

- Added a real diagnostics export from the app, available from the modern `Advanced` settings page.
- The export now produces a support-ready diagnostics folder with the current log, the current configuration file, and a system summary.

## 1.48.0 - Build 1048

- Hardened client distribution around an installer-only release flow.
- Added release integrity files with `SHA256SUMS.txt` and `RELEASE_MANIFEST.txt`.
- Cleaned the release packaging scripts and documentation so local distribution now matches the shipped product more closely.

## 1.45.0 - Build 1045

- Added save-confirmation visuals for both `Instant Replay` and manual `Record`.
- Saved clips now use a flash-and-shrink confirmation flow with a temporary thumbnail, real clip duration, and a direct click action to reveal the saved file in Windows Explorer.

## 1.43.0 - Build 1043

- Refactored the `Instant Replay` pipeline to better separate live capture, rolling buffer, and replay export.
- Replay export now runs in the background, with replay metrics added to logs for diagnosis and tuning.

## 1.40.0 - Build 1040

- Reworked the informational product pages in the modern `Settings` window.
- `About`, `Release notes`, `About the developer`, and `Legal` were cleaned up into a more product-like support area with direct actions for logs, GitHub, contact, and support links.

## 1.34.0 - Build 1034

- Switched the new custom `Settings` window to become the default user path.
- Kept the legacy `Settings` path available only as an explicit fallback for transition and verification.

## 1.23.0 - Build 1023

- Started the major refactor of `Settings` on a new custom UI foundation under `ui/`.
- Introduced the new layered base with Win32 shell, Direct2D/DirectWrite renderer, layout, input, scrolling, and page-driven rendering.

## 1.1.2 - Build 1012

- Unified the monitor rendering path around `Direct3D 11`.
- Moved screenshot and clipboard capture to the GPU final frame.
- Split recording logic into dedicated `Record` and `Instant Replay` handlers to prepare cleaner long-term evolution.

## 1.1.1 - Build 1011

- Hardened capture startup, shutdown, tray reduction, and signal/audio recovery.
- Reduced the impact of recording and replay work on live preview stability and responsiveness.

## 1.1.0 - Build 1010

- Turned the application into a real Windows software product instead of a portable-only utility.
- Added installer, uninstall support, Windows-standard storage paths, persistent configuration, and structured runtime logging.

## 1.0.9 - Build 1009

- Added the first dedicated foundations for manual recording and `Instant Replay`.
- Introduced user-facing controls, shortcuts, and output settings for both video save modes.

## 1.0.8 - Build 1008

- Added fullscreen scaling quality and enhanced sharpness options.
- Improved fullscreen display quality on higher-resolution monitors without altering the original HDMI source feed.

## 1.0.7 - Build 1007

- Added startup watcher behavior and tray integration.
- Introduced automatic launch options tied to signal detection and Windows startup.

## 1.0.6 - Build 1006

- Added screenshot capture via `F2` and quick clipboard copy support.
- Introduced animated capture feedback and direct opening of the saved screenshot from the temporary preview.

## 1.0.5 - Build 1005

- Added the first dedicated `Settings` window with structured categories such as `General`, `Startup`, `Captures`, `Audio`, `Video`, `Shortcuts`, and `Advanced`.

## 1.0.2 - Build 1002

- Reworked the monitor UI into a more product-oriented native Windows interface.
- Added stronger status feedback, clearer no-signal states, and persistence for key session settings.

## 1.0.1 - Build 1001

- Migrated the original portable concept into a dedicated native Windows application with its own codebase and monitor pipeline.

## 1.0.0 - Build 1000

- Original portable release.
