# Alya Live UI v1.1 — Java Edition Port

Ported for **Minecraft: Java Edition 1.21.11+** (resource pack format 75+).

## Source
- Original: *Alya Live UI v1.1* (Bedrock Edition resource pack) by RisabGamerz (Warrior Studios).
- Original Bedrock files are preserved in [`bedrock_source/`](bedrock_source/) (manifest, UI JSON, Bedrock textures, fonts, backgrounds, etc.).

## What was ported
- `pack.mcmeta` targeting Java pack format 75 with `supported_formats` for 1.21.11+.
- `pack.png` (from original `pack_icon.png`).
- GUI/container textures copied to `assets/minecraft/textures/gui/` (e.g. containers, advancements, book, bars, etc.).
- Misc textures copied to `assets/minecraft/textures/misc/` (e.g. vignette, pumpkin blur).
- Original font bitmap copied to `assets/minecraft/textures/font/default8.png` for reference.

## Limitations / notes
- **Bedrock UI JSON is not supported in Java Edition.** Custom menus, start screen layout, HUD layout, settings screens, and animated UI logic from `bedrock_source/ui/`, `bedrock_source/warrior/`, and `bedrock_source/rg_bg/` cannot be directly ported without mods.
- **Animated backgrounds** (`bedrock_source/Custom BG/`) rely on Bedrock UI/flipbook behavior and are not wired into vanilla Java.
- **Modern Java GUI changes:** Since 1.20+ (and especially 1.20.5+) many GUI elements moved to sprite-based textures under `assets/minecraft/textures/gui/sprites/`. Some textures from this pack may need manual remapping/splitting to fully apply on 1.21.11+.
- **Fonts:** Java uses a different font provider system (`assets/minecraft/font/*.json`); the Bedrock `default8.png` is included as-is and may require additional font provider JSON to take effect.

## Credits & permissions
See [`readme.txt`](readme.txt) and original author notes in [`bedrock_source/readme.txt`](bedrock_source/readme.txt). Redistribution/modification/commercial use restrictions from the original author apply.

## Forge mod packaging (added)
- Converted into a **Forge mod** project targeting **Minecraft 1.21.11** / **Forge 61.2.5** (Java 21).
- Mod ID: `alyaliveui` (client-side resource mod).
- Assets are packaged under `src/main/resources/assets/minecraft/`.
- Build config: `build.gradle`, `settings.gradle`, `gradle.properties`, `src/main/resources/META-INF/mods.toml`.
- Note: Gradle wrapper files (`gradlew`, `gradle/wrapper/*`) are not included; copy them from a matching Forge 1.21.11 MDK or generate with a local Gradle installation to build (`./gradlew build`).
