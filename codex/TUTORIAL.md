# Tutorial: turn one avatar image into a Codex Pet

**English | [中文](TUTORIAL.zh-CN.md)**

This is the exact process used to build the `pink-hanfu` pet in this repo.
Follow it with any other outfit from [`../muse/outfits/`](../muse/) and you get a
matching pet for that outfit — no coding background needed beyond running one
small Python script at the assembly step.

## What you are building

A Codex Pet is a plain folder with exactly two files:

```
<pet-id>/
├── pet.json
└── spritesheet.webp
```

| Requirement | Value |
|---|---|
| Format | Codex Pet v2 (`"spriteVersionNumber": 2` in pet.json) |
| Sprite sheet | 1536 × 2288 px, 8 columns × 11 rows |
| Cell | 192 × 208 px, transparent background, WebP or PNG |
| File size | under 20 MiB |
| Install location | `~/.codex/pets/<pet-id>/` (Windows: `%USERPROFILE%\.codex\pets\<pet-id>\`) |

## Step 1 — Prepare the source image

Start from one clean portrait of the character: big-head chibi style, upper body,
plain light background, the outfit you want the pet to wear. The images in
`muse/outfits/` (1600 × 1600) are exactly this. Keep this image open as the
reference for every drawing step — face, hairstyle and outfit details must not
drift between frames.

## Step 2 — Draw the 11 action strips, frame by frame

Do **not** animate one image with transforms — the result looks cheap. Instead,
draw one horizontal strip per animation row, with the exact frame count below,
using the source image as the character reference in your image generator.

| Row | State | Frames | What to draw |
|---|---|---|---|
| 0 | idle | 6 | subtle breathing, a blink; keep the laptop pose |
| 1 | running-right | 8 | running to the right, hair and sleeves flowing back |
| 2 | running-left | 8 | running to the left — you may mirror row 1 instead (the spec allows it) |
| 3 | waving | 4 | one hand raised, waving hello |
| 4 | jumping | 5 | crouch → leap → airborne → falling → landing |
| 5 | failed | 8 | stunned → drooping → slumped face-down on the keyboard |
| 6 | waiting | 6 | looking around, chin in hand, beckoning impatiently |
| 7 | running (working) | 6 | focused typing, hands alternating on the keyboard |
| 8 | review | 6 | leaning in to inspect, nodding, thumbs up |
| 9 | look directions A | 8 | gaze: up, up-right, right, down-right, down, down-left, left, up-left — head/eyes turning clockwise |
| 10 | look directions B | 8 | the same 8 directions continued at 22.5° steps (22.5°, 67.5°, … 337.5°) |

Prompt pattern that worked well:

> "Sprite strip of exactly N frames in a row, same big-head chibi girl as the
> reference image, same face, hairstyle and outfit, [action description],
> evenly spaced, plain white background, consistent character size in every frame"

Tips from the pink-hanfu build:

- **Count the frames in every returned strip.** One look-direction strip came
  back with 7 frames instead of 8; the missing 337.5° pose was drawn separately
  as a single image and inserted.
- Ask for generous spacing — wide poses (running) overlap their neighbours when
  spaced tightly, which makes slicing messy.
- Generate row 1 (running-right) well; row 2 can simply be its mirror.

## Step 3 — Slice the strips and clean the frames

Cut each strip into individual frames and remove the background so every frame
is transparent (the source background is plain, so flood-fill / edge-connected
removal works well). If poses are wider than the strip spacing, equal slicing
will cut faces — extract frames by connected components instead, and split any
merged pair at the projection valley. Afterwards, zoom into frame edges and
erase slivers of neighbouring frames; a hair-thin leftover strand is acceptable,
a visible chunk is not.

Scale every frame to fit a 192 × 208 cell, keeping one consistent character
scale and baseline across all rows.

## Step 4 — Assemble the sprite sheet

Place the frames on a 1536 × 2288 transparent canvas, 8 per row, in row order.
Two cells are special:

- Row 0, column 6: a **neutral front-facing pose** (reusing idle frame 1 works)
- Row 0, column 7 and every other unused cell: **fully transparent** — the
  validator rejects stray pixels there

Minimal assembly sketch (Python + Pillow):

```python
from PIL import Image

CELL_W, CELL_H, COLS = 192, 208, 8
sheet = Image.new("RGBA", (1536, 2288), (0, 0, 0, 0))
# frames[row] = list of RGBA frame images, already sized to fit a cell
for row, row_frames in enumerate(frames):
    for col, frame in enumerate(row_frames):
        sheet.alpha_composite(frame, (col * CELL_W, row * CELL_H))
sheet.save("spritesheet.webp", lossless=True)
```

## Step 5 — Write pet.json

```json
{
  "id": "teal-hanfu",
  "displayName": "Teal Hanfu",
  "description": "A big-head chibi cartoon girl with long black hair in a teal hanfu, typing on a small laptop. Every frame individually redrawn.",
  "spriteVersionNumber": 2,
  "spritesheetPath": "spritesheet.webp"
}
```

The `id` must match the folder name. Pick one id per outfit:

| Outfit image | Suggested pet id |
|---|---|
| `muse/avatar.webp` (Mon) | `pink-hanfu` ✅ already built |
| `muse/outfits/teal-hanfu.webp` (Tue) | `teal-hanfu` |
| `muse/outfits/purple-pearl-dress.webp` (Wed) | `purple-pearl-dress` |
| `muse/outfits/red-hanfu.webp` (Thu) | `red-hanfu` |
| `muse/outfits/light-blue-suit.webp` (Fri) | `light-blue-suit` |
| `muse/outfits/white-hanfu.webp` (Sat) | `white-hanfu` |
| `muse/outfits/pink-sweater.webp` (Sun) | `pink-sweater` |
| `muse/outfits/mint-qipao.webp` (spare) | `mint-qipao` |

## Step 6 — Validate before installing

- [ ] Sheet is exactly 1536 × 2288, transparent background
- [ ] Every used cell contains its frame; every unused cell is 100% transparent
- [ ] Frame counts per row match the table in Step 2 (74 used cells + neutral)
- [ ] `pet.json` parses, `spriteVersionNumber` is 2, `id` equals the folder name
- [ ] Total size under 20 MiB

## Step 7 — Install

Copy the finished folder into the pets directory, then in the ChatGPT / Codex
desktop app go to **Settings → Pets → Refresh**, select your pet, and toggle it
with `/pet`. Repeat per outfit — pets with different ids coexist, so you can
collect the whole wardrobe and switch any time.
