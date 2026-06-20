# Mindburner PAM — Firmware

PAM is a mono MIDI-to-CV converter (1V/oct, 12-bit DAC) with gate and S-Trig outputs, built around the ESP32. This repo hosts the firmware and a one-click browser-based installer — no Arduino IDE required.

## Install or update firmware

👉 **[Open the installer](https://mindburners.github.io/MINDBURNER-PAM-FIRMWARE/)**

1. Connect PAM to your computer via USB
2. Open the link above in **Chrome**, **Edge**, or **Opera**
3. Click **Connect**, choose the correct serial port, then click **Install**

That's it — no drivers or software to install beyond your browser.

> ⚠️ Not supported in Safari or Firefox (no Web Serial support).

## MIDI input modes

PAM supports two MIDI input sources:

| Mode | How to boot into it |
|---|---|
| **DIN MIDI** (default) | Power on normally |
| **BLE MIDI** | Hold button **C** while powering on |

The header colour and a short on-screen banner confirm which mode is active at boot. In BLE mode, PAM advertises as `MB_PAM` — pair to it from your MIDI source.

## What's in this repo

| File | Purpose |
|---|---|
| `index.html` | The installer page |
| `manifest.json` | Tells the installer where each firmware part goes in flash |
| `bootloader.bin`, `partitions.bin`, `firmware.bin` | The compiled firmware |
| `logo.png` | Branding shown on the installer page |

## Releasing an update

1. In Arduino IDE: **Sketch → Export Compiled Binary**
2. Rename the three exported files to `bootloader.bin`, `partitions.bin`, `firmware.bin`
3. Drag them into this repo, overwriting the existing files
4. Done — the installer link above always serves the latest version

## Hardware

- ESP32-WROOM-32E
- ST7735 160×128 SPI colour TFT
- MCP4725 12-bit DAC
- 3-button interface (cycle channel, transpose, calibration mode)

---
Mindburner — Alan G. Watkins
