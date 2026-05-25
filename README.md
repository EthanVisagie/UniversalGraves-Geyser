# UniversalGraves-Geyser

UniversalGraves-Geyser is a Fabric addon that improves Bedrock Edition support for [Universal Graves](https://modrinth.com/mod/universal-graves) when players connect through Geyser and Floodgate.

Universal Graves uses Polymer to render custom grave blocks and GUIs for Java players. Bedrock clients connected through Geyser can miss those virtual visuals. This addon provides Bedrock-friendly grave overlays and GUI translations.

## Features

- visual grave overlays for Bedrock players
- skull block markers at grave positions
- floating grave text
- item previews near graves
- GUI translation for custom player-head buttons
- protection against graves being destroyed during slow server loads
- automatic overlay cleanup when graves are collected or destroyed

## Requirements

- Minecraft Java `1.21.11`
- Fabric Loader `0.18.6` or newer
- Fabric API
- Universal Graves `3.10.2+1.21.11`
- Geyser
- Floodgate, recommended for Bedrock player detection

## Installation

1. Install Fabric for your Minecraft server version.
2. Install Fabric API.
3. Install Universal Graves.
4. Install Geyser and Floodgate.
5. Put the UniversalGraves-Geyser jar in your server `mods` folder.
6. Restart the server.

## Downloads

Use the approved Modrinth or CurseForge project page when available. Development builds may also be attached to GitHub releases for this repository.

## How It Works

For Bedrock players within range of a grave, the mod renders a Bedrock-visible overlay using real block states and fake entities. This gives Bedrock players a visible grave location instead of relying only on Polymer virtual blocks.

When a Bedrock player opens the grave UI, custom player head buttons are replaced with recognizable vanilla items such as arrows and barriers.

## Known Limits

- This addon is intended for servers using Geyser and Universal Graves.
- Java players should continue to see the normal Universal Graves behavior.
- Bedrock visuals are compatibility overlays, not a full replacement for Universal Graves.
- Other grave mods are not supported unless explicitly listed in a release note.

## Reporting Issues

Open issues on this repository for bugs in this addon.

Include:

- Minecraft version
- Fabric Loader version
- Universal Graves version
- Geyser and Floodgate versions
- whether the affected player is Java or Bedrock
- screenshots when the issue is visual
- `latest.log` or the crash report

## Building From Source

```bash
./gradlew build
```

Built jars are written to `build/libs`.

The build uses Java 21.

## Releasing

1. Commit the release changes.
2. Create and push a tag such as `v1.0.1-beta.2` for a beta or `v1.0.1` for a stable release.
3. GitHub Actions builds the jars on Java 21 and attaches them to the GitHub release.

Tags containing `beta`, `alpha`, or `rc` are published as prereleases.

## Credits

UniversalGraves-Geyser is an addon for Universal Graves. Universal Graves, Polymer, Geyser, and Floodgate are separate projects maintained by their respective authors.
