# USB HDMI Monitor

🇫🇷 Version française :
[README_FR.md](./README_FR.md)

USB HDMI Monitor is a lightweight native Windows monitor for USB HDMI capture adapters.

It is designed for people who want to display a console or another HDMI source on a PC without the overhead of OBS when they do not need streaming or scene management.

This public repository is the product hub for USB HDMI Monitor:
- release binaries
- screenshots and media
- changelog and documentation

The source code is maintained separately in a private repository.

![USB HDMI Monitor - In game preview](./media/screenshots/Console_On1.png)

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

Latest public release:
- [`USB HDMI Monitor v1.0.0`](https://github.com/Azashiin/USBHDMIMonitor/releases/tag/v1.0.0)

Direct download:
- [`USBHDMIMonitor-v1.0.0-win64.zip`](https://github.com/Azashiin/USBHDMIMonitor/releases/download/v1.0.0/USBHDMIMonitor-v1.0.0-win64.zip)

All future builds will be published through the repository `Releases` page:
- [`Releases`](https://github.com/Azashiin/USBHDMIMonitor/releases)

## Screenshots

### HDMI Preview

**No signal state**

![USB HDMI Monitor - No signal](./media/screenshots/Console_Off.png)

**Console connected**

![USB HDMI Monitor - Console menu](./media/screenshots/Console_On2.png)

### Settings

**General settings**

![USB HDMI Monitor - General settings](./media/screenshots/Settings_general.png)

**Capture settings**

![USB HDMI Monitor - Capture settings](./media/screenshots/Settings_capture.png)

**Shortcut settings**

![USB HDMI Monitor - Shortcut settings](./media/screenshots/Settings_shortcut.png)

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
