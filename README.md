# USB HDMI Monitor

USB HDMI Monitor is a lightweight native Windows monitor for USB HDMI capture adapters.

It is designed for people who want to display a console or another HDMI source on a PC without the overhead of OBS when they do not need streaming or scene management.

This public repository is the product hub:
- release binaries
- screenshots and media
- changelog and documentation

The source code is maintained separately in a private repository.

## Why Use It

- Faster and simpler than opening a full broadcast suite
- Low-friction HDMI preview for USB UVC capture dongles
- Fullscreen mode with local GPU upscaling
- Automatic audio monitoring when Windows exposes a matching audio endpoint
- Screenshot capture with preview
- Optional Windows startup watcher for automatic source detection

## Best For

- Console players using a cheap USB HDMI capture dongle as a software screen
- Users who want a clean HDMI viewer on PC
- People who do not need OBS scenes, streaming setup, or recording workflows

## Download

Current local release package:
- [`releases/latest/USBHDMIMonitor.exe`](./releases/latest/USBHDMIMonitor.exe)

When published on GitHub, the recommended distribution path is the repository `Releases` page.

## Tested Hardware

USB HDMI Monitor is primarily designed and tested around USB UVC HDMI capture adapters.

Important:
- compatibility depends on what the capture device, USB link, and HDMI source actually expose
- this is not positioned as a universal professional broadcast capture solution
- this project is not affiliated with the manufacturer of any capture dongle

## Current Feature Set

- device, resolution, and frame-rate selection
- fullscreen monitor mode
- audio volume control
- screenshot capture
- configurable shortcuts
- settings window
- tray integration and startup watcher

## Project Status

This public repository intentionally does not contain the application source code.

It exists to:
- present the project publicly
- distribute builds
- provide screenshots and release notes

## License And Distribution

See [`LICENSE.txt`](./LICENSE.txt).
