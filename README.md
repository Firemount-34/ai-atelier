# AI Atelier — Virtual Avatars & Codex Pets

**English | [中文](README.zh-CN.md)**

> The workshop of **AI造物局** (AI Atelier): a collection of big-head chibi
> avatar looks. Every character lives in its own numbered folder, split by
> platform — `muse/` holds the Muse avatar assets, `codex/` holds the Codex
> desktop pet (built, or planned with a suggested pet id).

## Characters

| 01 · Pink hanfu | 02 · Teal hanfu | 03 · Purple pearl dress | 04 · Red hanfu | 05 · Light blue suit |
|---|---|---|---|---|
| ![01](01-pink-hanfu/muse/avatar.webp) | ![02](02-teal-hanfu/muse/avatar.webp) | ![03](03-purple-pearl-dress/muse/avatar.webp) | ![04](04-red-hanfu/muse/avatar.webp) | ![05](05-light-blue-suit/muse/avatar.webp) |

| 06 · White hanfu | 07 · Pink sweater | 08 · Mint qipao | 09 · Lin Yiyi | 10 · Twin-tails |
|---|---|---|---|---|
| ![06](06-white-hanfu/muse/avatar.webp) | ![07](07-pink-sweater/muse/avatar.webp) | ![08](08-mint-qipao/muse/avatar.webp) | ![09](09-lin-yiyi/muse/avatar.webp) | ![10](10-twin-tails/muse/avatar.webp) |

| # | Character | Notes | Codex pet |
|---|---|---|---|
| 01 | [Pink hanfu](01-pink-hanfu/) · 粉白刺绣古装 | Monday of the weekly rotation; the original main avatar | ✅ built |
| 02 | [Teal hanfu](02-teal-hanfu/) · 青绿古装 | Tuesday | planned |
| 03 | [Purple pearl dress](03-purple-pearl-dress/) · 紫色珍珠礼服 | Wednesday | planned |
| 04 | [Red hanfu](04-red-hanfu/) · 红色金纹古装 | Thursday | planned |
| 05 | [Light blue suit](05-light-blue-suit/) · 浅蓝西装现代装 | Friday | planned |
| 06 | [White hanfu](06-white-hanfu/) · 白衣仙气古装 | Saturday | planned |
| 07 | [Pink sweater](07-pink-sweater/) · 粉色毛衣日常装 | Sunday | planned |
| 08 | [Mint qipao](08-mint-qipao/) · 薄荷绿旗袍 | Spare outfit | planned |
| 09 | [Lin Yiyi](09-lin-yiyi/) · 林一一 | Q-version Lin Yiyi from the Douyin drama 《我的妹妹不可爱》; Muse avatar since 2026-11-20 | planned |
| 10 | [Twin-tails](10-twin-tails/) · 原创双马尾 | Fully original pixel-art chibi girl | planned |

Characters 01–08 are one character in eight outfits — big-head, upper-body,
typing on a small laptop — rotated weekly as the Muse assistant's avatar.
09 and 10 are separate looks in a pixel-art chibi style.

## Repository layout

```
.
├── README.md / README.zh-CN.md   # this page
├── TUTORIAL.md / TUTORIAL.zh-CN.md
│                                 # how to turn any look into a Codex pet
├── 01-pink-hanfu/                # one numbered folder per character
│   ├── README.md                 # character overview
│   ├── muse/                     # Muse avatar assets (+ README)
│   └── codex/                    # Codex pet package or plan (+ README)
├── 02-teal-hanfu/
├── ...
└── 10-twin-tails/
```

## The Codex pet

So far only **01 · Pink hanfu** has a pet: a Codex Pet v2 package redrawn
frame by frame (8 columns × 11 rows, 1536×2288). Full spec, previews and
install guide: [`01-pink-hanfu/codex/`](01-pink-hanfu/codex/).

![Codex sprite sheet](01-pink-hanfu/codex/preview/contact-sheet.png)

| idle | waving | working | jumping |
|---|---|---|---|
| ![idle](01-pink-hanfu/codex/preview/idle.gif) | ![waving](01-pink-hanfu/codex/preview/waving.gif) | ![working](01-pink-hanfu/codex/preview/working.gif) | ![jumping](01-pink-hanfu/codex/preview/jumping.gif) |

**Install**: copy `01-pink-hanfu/codex/pink-hanfu/` into `~/.codex/pets/`
(Windows: `%USERPROFILE%\.codex\pets\`), then in the ChatGPT / Codex desktop
app go to **Settings → Pets → Refresh** and select **"粉白古装 · Pink Hanfu"**.

Want a pet for another character? Follow [**TUTORIAL.md**](TUTORIAL.md) —
the full pipeline, with a suggested pet id per character.

## Disclaimer

Personal, non-commercial works. The characters are stylized cartoon
depictions, unrelated to any real person or to OpenAI, Meta, or any other
company. Please do not use commercially. Character 09 is a fan work; see its
own folder for details.
