# UniversalGraves-Geyser

A Fabric mod that adds Bedrock Edition (Geyser/Floodgate) compatibility to [Universal Graves](https://modrinth.com/mod/universal-graves).

## Features

- **Visual Grave Overlays**: Bedrock players see skull blocks, floating text displays, and item previews at grave locations
- **GUI Translation**: Replaces Polymer's custom player head buttons with recognizable vanilla items in the grave UI
- **Grave Protection**: Prevents graves from being destroyed during slow server loads
- **Automatic Cleanup**: Overlays are properly removed when graves are collected or destroyed

## Why This Mod?

Universal Graves uses [Polymer](https://github.com/Patbox/polymer) to render custom blocks and GUIs. While this works great for Java Edition players, Bedrock Edition players connecting via Geyser see:
- Invisible grave blocks (Polymer virtual blocks)
- Steve heads instead of custom GUI buttons

This addon fixes both issues by:
1. Sending real block states and fake entities to Bedrock players
2. Intercepting GUI packets and translating custom heads to vanilla items

## Requirements

- **Minecraft Java**: 1.21.10 (tested)
- **Fabric Loader**: 0.14.0+
- **Fabric API**
- **Universal Graves**: 3.9.1+
- **Floodgate** (recommended): For detecting Bedrock players

## Installation

1. Install [Fabric](https://fabricmc.net/) for your Minecraft version
2. Install [Fabric API](https://modrinth.com/mod/fabric-api)
3. Install [Universal Graves](https://modrinth.com/mod/universal-graves)
4. Install [Geyser](https://geysermc.org/) and [Floodgate](https://wiki.geysermc.org/floodgate/)
5. Download this mod and place it in your `mods` folder

## Building from Source

```bash
# Clone the repository
git clone https://github.com/EthanVisagie/UniversalGraves-Geyser.git
cd UniversalGraves-Geyser

# Build the mod
./gradlew build

# The jar will be in build/libs/
```

## How It Works

### Grave Overlays
For Bedrock players within 48 blocks of a grave:
- A skeleton skull block is rendered at the grave position
- An invisible armor stand displays grave information (owner, items, XP, timers)
- An invisible fox holds a preview of the first item in the grave

### GUI Translation
When a Bedrock player opens the grave UI:
- Custom player head buttons are replaced with vanilla items
- "Next" → Arrow
- "Previous" → Arrow
- "Close" → Barrier
- "Collect" → Chest
- And more...

## Configuration

Currently all settings are hardcoded.

## Status 
Experimental but working on our production server. Config file support planned when there is feedback.

| Setting | Value | Description |
|---------|-------|-------------|
| Render Distance | 48 blocks | Maximum distance to show overlays |
| Update Rate | 5 ticks (0.25s) | How often overlays are updated |
| Respawn Interval | 30 seconds | How often entities are respawned |

## Compatibility

- **Universal Graves**: Required, tested with 3.9.1+
- **Geyser/Floodgate**: Required for Bedrock player detection
- **Other mods**: Should be compatible with most server-side mods

## License

MIT License - See [LICENSE](LICENSE) for details.

## Credits

- [Universal Graves](https://modrinth.com/mod/universal-graves) by Patbox
- [Polymer](https://github.com/Patbox/polymer) by Patbox
- [SGUI](https://github.com/Patbox/sgui) by Patbox
- [Geyser](https://geysermc.org/) and [Floodgate](https://wiki.geysermc.org/floodgate/) teams

## Issues

Found a bug? Please report it on [GitHub Issues](https://github.com/EthanVisagie/UniversalGraves-Geyser/issues).
