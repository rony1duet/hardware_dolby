# LunarisDolby

[![Android](https://img.shields.io/badge/Platform-Android_14%2B-green.svg)](https://android.com)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)
[![Material 3](https://img.shields.io/badge/Design-Material_3_Expressive-purple.svg)](https://m3.material.io)
[![Maintainer](https://img.shields.io/badge/Maintainer-rony1duet-blueviolet.svg)](https://github.com/rony1duet)

Modern **Dolby Atmos** audio management application written with **Jetpack Compose Material 3 Expressive**, designed for AOSP-based custom ROMs and systemless deployment (KernelSU / Magisk / APatch).

---

## ✨ Features

- **🎨 Modern Material 3 Expressive Design**:
  - Full dynamic color extraction and Material You theming.
  - Interactive profile selector carousel (Dynamic, Movie, Music, Voice, Game, Custom).
  - Modern bottom navigation bar with fluid transitions.

- **⚡ Real-Time Quick Settings Sync**:
  - Instant bi-directional state synchronization between the Quick Settings Dolby tile and the application.
  - No need to restart the app to reflect toggled Dolby Atmos states.

- **🎛️ Advanced Equalizer & Tuning**:
  - Multi-band interactive equalizer with Bezier curve visualization and draggable sliders (10, 15, and 20 bands).
  - Bass Enhancer, Mid Enhancer, Treble Enhancer with customizable curves.
  - Volume Leveler and Dialogue Enhancer support.
  - Custom preset import & export system (JSON file format).

- **📱 Per-App Audio Profiles**:
  - Dynamically switches Dolby Atmos profiles when specific foreground apps are launched.
  - Headphone & Bluetooth only mode toggle.
  - Searchable installed application list with profile selection.

- **⚙️ Device-Specific Memory**:
  - Remembers distinct EQ and Dolby profile configurations per connected device (Speaker, Headset, Bluetooth A2DP).

- **🚀 Systemless KernelSU / Magisk Module Compatibility**:
  - Seamlessly replaces stock `co.aospa.dolby` and other outdated Dolby manager implementations.
  - Pre-configured SELinux contexts, permissions, and vendor manifest integration.

---

## 🛠️ Project Structure

```
LunarisDolby/
├── Android.bp                                 # Android Build Blueprint
├── AndroidManifest.xml                        # Manifest with Settings IA integration
├── privapp-permissions-dolby.xml              # Privileged system permissions
├── preinstalled-packages-platform-dolby.xml   # Pre-installed package definitions
├── res/                                       # Strings, drawables, and themes
└── src/org/lunaris/dolby/
    ├── data/                                  # Data repositories & HAL bridge
    ├── domain/                                # UI state models
    ├── service/                               # QS TileService & app monitor
    └── ui/                                    # Compose screens & components
        ├── components/                        # Expressive UI components
        ├── screens/                           # Main, Equalizer, Per-App screens
        └── theme/                             # M3 Typography, Shapes & Colors
```

---

## 🚀 Installation

### Via KernelSU / Magisk / APatch
1. Grab the latest flashable module ZIP (`LunarisDolby_Magisk_Module.zip`).
2. Flash in **KernelSU Manager**, **Magisk Manager**, or **APatch**.
3. Reboot your device to apply the systemless priv-app mounts.

### Building from Source (AOSP Tree)
Place this repository into your ROM tree under `packages/apps/LunarisDolby`:
```bash
git clone https://github.com/rony1duet/LunarisDolby.git packages/apps/LunarisDolby
```
Add `LunarisDolby` to `PRODUCT_PACKAGES` in your device configuration:
```make
PRODUCT_PACKAGES += \
    LunarisDolby
```

---

## 👤 Maintainer

- **MD RONY HOSSEN** ([@rony1duet](https://github.com/rony1duet))

---

## 📄 License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for details.
