# LunarisDolby

Dolby Atmos audio management application built with Jetpack Compose (Material 3). Designed for custom ROM trees and systemless installation via KernelSU, Magisk, or APatch.

## Features

- **Material You UI:** Dynamic color theming and preset carousel (Dynamic, Movie, Music, Voice, Game, Custom).
- **Quick Settings Tile Sync:** Real-time state synchronization between the Dolby QS tile and app preferences without requiring an app restart.
- **Parametric Equalizer:** Multi-band graphic equalizer with presets and JSON import/export support.
- **Audio Enhancement:** Dialogue Enhancer, Bass Enhancer, and Volume Leveler controls.
- **Per-App Audio Profiles:** Automatically switches audio profiles based on the active foreground app.
- **Per-Endpoint Settings:** Retains separate equalizer and profile configurations for Speaker, Headset, and Bluetooth devices.

## Project Structure

```text
LunarisDolby/
├── Android.bp                                 # Soong blueprint
├── AndroidManifest.xml                        # App manifest & settings injection
├── privapp-permissions-dolby.xml              # Privileged permissions whitelist
├── preinstalled-packages-platform-dolby.xml   # Platform package declarations
├── res/                                       # Strings, icons, and themes
└── src/org/lunaris/dolby/
    ├── data/                                  # Audio HAL IPC and preferences
    ├── domain/                                # State models
    ├── service/                               # QS tile service & audio routing monitor
    └── ui/                                    # Compose screens and viewmodels
```

## Installation

### Via KernelSU / Magisk / APatch
1. Download the flashable module zip from [Releases](../../releases).
2. Flash in KernelSU, Magisk, or APatch.
3. Reboot to apply systemless priv-app mounts.

### AOSP / ROM Source Integration
Clone to `packages/apps/LunarisDolby` or include via local manifest:
```bash
git clone https://github.com/rony1duet/hardware_dolby.git -b PixelOS-17-base hardware/dolby
```

Add `LunarisDolby` to `PRODUCT_PACKAGES` in your device makefile:
```makefile
PRODUCT_PACKAGES += \
    LunarisDolby
```

## License

Licensed under [Apache 2.0](LICENSE).
