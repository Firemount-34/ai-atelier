# codex/ — Codex Pet

**[中文](README.md) | English**

Codex Pet v2 import package. The character is the same one as the avatar in this repository, and every frame was redrawn individually.

## Install

Copy the whole `pink-hanfu/` folder to:

- macOS / Linux: `~/.codex/pets/pink-hanfu/`
- Windows: `%USERPROFILE%\.codex\pets\pink-hanfu\`
- With `CODEX_HOME` set: `$CODEX_HOME/pets/pink-hanfu/`

The folder must directly contain `pet.json` and `spritesheet.webp`
(no extra nesting). Then open the ChatGPT / Codex desktop app →
Settings → Pets → Refresh, and select "粉白古装 · Pink Hanfu".

## Files

| Path | Description |
|---|---|
| `pink-hanfu/pet.json` | Manifest: id / displayName / description / spriteVersionNumber 2 / spritesheetPath |
| `pink-hanfu/spritesheet.webp` | Sprite sheet: 1536×2288, 8×11, 192×208 per cell, transparent, ~1.7 MB |
| `preview/contact-sheet.png` | Full sheet preview |
| `preview/*.gif` | Animated previews: idle / waving / working / jumping |

See the repository root [README](../README.en.md) for the full spec and row-by-row breakdown.
