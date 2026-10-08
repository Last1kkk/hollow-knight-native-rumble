# Hollow Knight Native Rumble — macOS

Restores native controller rumble in Hollow Knight 1.5.75 on macOS while preserving Hollow Knight's original vibration system and patterns.

## Platform

- macOS only

## Game

- Hollow Knight 1.5.75

## Architecture

- Hollow Knight native macOS x86_64 build running under Rosetta on Apple Silicon
- The native haptics component is macOS-specific

## Tested environment

- macOS Tahoe 26.6.2 (25G83)
- Apple Silicon M4 Pro
- 24 GB RAM

## Tested controller

- 8BitDo Ultimate 2 Bluetooth Controller
- Switch version
- Bluetooth mode
- macOS identifies it as Nintendo Switch Pro Controller / Pro Controller

## Compatibility

Designed to work with macOS-compatible controllers supported by Hollow Knight/InControl with rumble capability. Only the 8BitDo Ultimate 2 Bluetooth Controller has been tested so far.

## How it works

The mod does not manually assign arbitrary vibration patterns to game events. It restores the game's normal vibration pipeline:

```
game event
→ Hollow Knight VibrationManager
→ GamepadVibrationMixer
→ original AnimationCurve / PlaybackRate / Loop / mixing
→ final motor values
→ InControl_SetHapticState
→ native macOS haptics hook
→ CoreHaptics
→ controller
```

This preserves the game's original vibration behavior rather than replacing it with a manually constructed vibration table.

## Installation

1. Install the mod using Lumafly.
2. The release contains `HKHapticsMod.dll` and `MyTool`.
3. No Steam, CrossOver, ControllerFixes, or external Windows components are required by this mod.
4. Launch Hollow Knight through Lumafly.

## Limitations

- macOS only.
- Tested on macOS Tahoe 26.6.2.
- Only the 8BitDo Ultimate 2 Bluetooth Controller has been tested so far.
- No intensity setting/menu is included in v1.0.0.

## Version

v1.0.0
