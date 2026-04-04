# Changelog

## 1.0.1 - 2026-04-04

- Add support for Minecraft 1.21.11 and remove the upper-bound loader version check that rejected newer 1.21.x servers.
- Update Fabric, Universal Graves, SGUI, and Polymer dependency lines for the 1.21.11 release line.
- Upgrade Fabric Loom to 1.13.4 and disable mod-provided javadocs to match the dependency toolchain used by the 1.21.11 stack.
- Pin the project to Java 21 with Gradle toolchains and automatic resolver support so local and CI builds do not depend on a manually set `JAVA_HOME`.
