# USB HDMI Monitor 1.52.1 — public preview test guide

## Without an adapter

Run the installer, then use the **Demo pattern** shortcut in the Start menu, or choose **Demo pattern** in the app. The shortcut launches the installed app with `--demo`. No capture device or audio endpoint is opened in demo mode.

Open **Picture** and try Standard, Cinema, Game, Dynamic and Custom. Brightness, contrast and color use 50 as the neutral value; sharpness uses 0. Try Warm, Neutral and Cool temperature. Each mode keeps its own settings; **Reset this mode** affects only the selected mode.

**Show original picture** temporarily bypasses all image adjustments and ICC. Scroll the inspector on shorter windows. Mode and temperature menus also accept arrow keys, Enter and Escape.

Under **Advanced**, gamma is neutral at 1.00; tint and RGB channels are neutral at 50. Optional ICC management accepts RGB ICC/ICM input/display profiles, defaults to an sRGB source and detects the current Windows display profile. It offers perceptual, relative colorimetric, saturation and absolute colorimetric intents. Wait for the ICC transform-ready state before taking a screenshot. Invalid or missing profiles are rejected.

These controls adjust the video image, not the physical display backlight. Game mode is a picture preset and does not change capture timing. The pipeline is 8-bit SDR; it does not implement HDR or measured calibration. Recordings and replays keep source colors. Screenshots are converted to sRGB, except when original comparison bypasses conversion.

## With a USB HDMI adapter

Run `USBHDMIMonitor.exe` normally or leave demo mode. The app scans devices and may automatically open the selected source. Select the correct adapter, resolution and frame rate.

1. Check picture and audio for at least 15 minutes, including fullscreen and windowed viewing.
2. Try a black frame, dark scenes, fast motion and a reference pattern from the HDMI source. Note black levels, smoothness and any audio delay.
3. Unplug/reconnect the adapter, power-cycle the HDMI source and change resolution. Check recovery without a freeze.
4. Save a PNG and copy an image with Ctrl+C. Open the saved file; also try JPEG from Settings.
5. Record an MP4 with audio and play it back. After at least 35 seconds, save two replays several seconds apart and check their durations and playback.
6. Try picture adjustments and a known ICC profile. With differently profiled displays, move the window between them and check the automatic destination profile.
7. Restart the app and confirm that per-mode values, profiles and rendering intent persist. Also test minimize-to-tray and restore.

## Shortcuts and storage

F2: screenshot. Ctrl+C: copy. F9: start/stop recording. F3: replay. F10: settings. F11: fullscreen. Esc: exit fullscreen. M: mute.

Settings: `%APPDATA%\USB HDMI Monitor`. Picture preferences: `USBHDMIMonitor.ini.color.ini`. Imported ICC paths refer to the original files, so keep those files in place. Logs: `%LOCALAPPDATA%\USB HDMI Monitor\Logs`. Export diagnostics from **Settings > Advanced** when needed.

## Validation

`VALIDATION_RESULTS.txt` lists 32 passing native checks plus release checks. They exercise synthetic media, picture-mode memory, migration, white balance, sharpness, GPU/WARP rendering, ICC conversion, Unicode paths and release metadata. Hardware capture, audio, USB reconnections and long sessions remain to be verified by testers.

For feedback, provide app version, adapter model, HDMI source, resolution/frame rate, Windows version and exact reproduction steps in the repository's issues. Review any diagnostic archive before sharing it.
