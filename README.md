# Pink Hanfu — Virtual Avatar & Codex Pet

**English | [中文](README.zh-CN.md)**

> A two-platform asset repo for one big-head chibi character: `muse/` holds her
> avatar assets for Muse — all eight outfits of her wardrobe — and `codex/` holds
> a Codex desktop pet import package redrawn frame by frame from the Monday
> outfit, plus a tutorial for making pets of the other outfits.

![Avatar](muse/avatar.webp)

## The character

- **Look**: big-head chibi cartoon girl, long straight black hair with a center part, pearl earrings
- **Signature pose**: typing on a small laptop
- **Wardrobe**: eight outfits — a seven-outfit weekly rotation (Mon–Sun) plus one spare. The pet in this repo wears the Monday outfit: a pink-and-white hanfu with gold-thread embroidery
- **Origin**: originally a custom avatar for the Muse personal assistant, later fully redrawn as an importable animated Codex pet

## The wardrobe

| Mon · Pink hanfu | Tue · Teal hanfu | Wed · Purple pearl dress | Thu · Red hanfu |
|---|---|---|---|
| ![Mon](muse/avatar.webp) | ![Tue](muse/outfits/teal-hanfu.webp) | ![Wed](muse/outfits/purple-pearl-dress.webp) | ![Thu](muse/outfits/red-hanfu.webp) |

| Fri · Light blue suit | Sat · White hanfu | Sun · Pink sweater | Spare · Mint qipao |
|---|---|---|---|
| ![Fri](muse/outfits/light-blue-suit.webp) | ![Sat](muse/outfits/white-hanfu.webp) | ![Sun](muse/outfits/pink-sweater.webp) | ![Spare](muse/outfits/mint-qipao.webp) |

Files: Monday is [`muse/avatar.webp`](muse/avatar.webp); the rest live in
[`muse/outfits/`](muse/outfits/).

## Another avatar — Lin Yiyi

[`muse/lin-yiyi/`](muse/lin-yiyi/) holds a Q-version avatar of Lin Yiyi （林一一）
from the Douyin drama 《我的妹妹不可爱》 ("My Sister Is Not Cute"), the active
Muse avatar since 2026-11-20. A separate look from the pink-hanfu character above.

![Lin Yiyi](muse/lin-yiyi/avatar.webp)

## Preview

The full Codex sprite sheet (8 columns × 11 rows):

![Codex sprite sheet](codex/preview/contact-sheet.png)

| idle | waving | working | jumping |
|---|---|---|---|
| ![idle](codex/preview/idle.gif) | ![waving](codex/preview/waving.gif) | ![working](codex/preview/working.gif) | ![jumping](codex/preview/jumping.gif) |

## Repository layout

```
.
├── README.md                  # this page (English)
├── README.zh-CN.md            # 中文说明
├── muse/                      # Muse platform assets
│   ├── avatar.webp            # main avatar — Monday outfit (1600×1600)
│   ├── outfits/               # the other 7 outfits (Tue–Sun + spare)
│   ├── states/                # dark-mode state images (Monday outfit)
│   ├── lin-yiyi/              # Q-version Lin Yiyi avatar (separate look)
│   └── README.md
└── codex/                     # Codex platform pet
    ├── pink-hanfu/
    │   ├── pet.json           # pet manifest (spriteVersionNumber: 2)
    │   └── spritesheet.webp   # sprite sheet (1536×2288, transparent)
    ├── preview/               # contact sheet and animated previews
    ├── TUTORIAL.md            # make a pet for any other outfit
    └── README.md              # install guide
```

## Installing the Codex pet (local import)

1. Copy the whole `codex/pink-hanfu/` folder into Codex's pets directory:
   - macOS / Linux: `~/.codex/pets/`
   - Windows: `%USERPROFILE%\.codex\pets\`
   - If `CODEX_HOME` is set: `$CODEX_HOME/pets/`
2. Open the ChatGPT / Codex desktop app → **Settings → Pets → Refresh**
3. Select **"粉白古装 · Pink Hanfu"**, and toggle it any time with `/pet`

Want a pet wearing a different outfit? Follow
[**codex/TUTORIAL.md**](codex/TUTORIAL.md) — it walks through the whole process,
from one outfit image in `muse/outfits/` to an installable pet package.

## Sprite sheet spec

| Item | Value |
|---|---|
| Format | Codex Pet v2 |
| Sheet size | 1536 × 2288 px (8 columns × 11 rows) |
| Cell | 192 × 208 px, transparent WebP |
| Frames | 74 used cells (plus a neutral front-facing cell) |

| Row | State | Frames | Content |
|---|---|---|---|
| 0 | idle | 6 (+ neutral) | breathing, blinking |
| 1 | running-right | 8 | running right, hair flowing back |
| 2 | running-left | 8 | running left (mirror-derived from the right run, allowed by the spec) |
| 3 | waving | 4 | raising a hand to say hello |
| 4 | jumping | 5 | crouch, leap, airborne, fall, landing |
| 5 | failed | 8 | from stunned and drooping to face-down on the keyboard |
| 6 | waiting | 6 | looking around, chin in hand, beckoning |
| 7 | running (working) | 6 | focused typing |
| 8 | review | 6 | leaning in to inspect, nodding, thumbs up |
| 9–10 | look directions | 16 | clockwise from straight up, one gaze every 22.5° |

## Production notes

- Every frame was **individually redrawn** — no displacement/scale transforms of a single image: expressions, poses and hair movement differ frame by frame
- The look-direction set originally had only 7 of 8 frames drawn; the missing 337.5° frame was drawn separately to complete it
- Assembly only did background removal, frame slicing and size normalization; a few frames may keep a hair-thin strand from a neighbouring frame at the edge, essentially invisible at actual pet display size

## Disclaimer

A personal, non-commercial fan work. The character is a stylized cartoon depiction, unrelated to any real person or to OpenAI, Meta, or any other company. Please do not use commercially.
