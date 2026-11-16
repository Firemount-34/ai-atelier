# codex/ — Codex Pet

**English | [中文](README.zh-CN.md)**

Codex Pet v2 import package. The character is the same one as the avatar in
this repository, wearing the Monday outfit, and every frame was redrawn
individually.

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
| `TUTORIAL.md` | How to make a pet for any other outfit |

See the repository root [README](../README.md) for the full spec and row-by-row breakdown.

## Make a pet for another outfit

Only the Monday outfit has a ready-made pet in this repo. For the other seven
outfits in [`../muse/outfits/`](../muse/), follow
[**TUTORIAL.md**](TUTORIAL.md): it documents the whole pipeline used for this
pet — drawing the 11 action strips frame by frame, slicing and cleaning,
assembling the 1536×2288 sheet, writing `pet.json`, validating, and installing —
including a suggested pet id per outfit.
