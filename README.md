# AI Atelier — Virtual Avatars & Codex Pets

**English | [中文](README.zh-CN.md)**

> The workshop of **AI造物局** (AI Atelier): a collection of big-head chibi
> avatar characters. Each character has its own numbered folder; inside,
> every look is split by platform — `muse/` holds the Muse avatar assets,
> `codex/` holds the Codex desktop pet (built, or planned with a suggested
> pet id).

## Characters

| # | Character | Looks | Codex pet |
|---|---|---|---|
| 01 | [The Main Avatar](01-main-avatar/) · 主形象 | One character, 8 outfits in a weekly rotation (Mon–Sun + spare) | ✅ pink hanfu built, rest planned |
| 02 | [Lin Yiyi](02-lin-yiyi/) · 林一一 | Q-version Lin Yiyi from the Douyin drama 《我的妹妹不可爱》; Muse avatar since 2026-11-20 | planned |
| 03 | [Twin-tails](03-twin-tails/) · 原创双马尾 | Fully original pixel-art chibi girl | planned |

### 01 · The Main Avatar — 8 outfits

| Mon · Pink hanfu | Tue · Teal hanfu | Wed · Purple pearl dress | Thu · Red hanfu |
|---|---|---|---|
| ![Mon](01-main-avatar/01-pink-hanfu/muse/avatar.webp) | ![Tue](01-main-avatar/02-teal-hanfu/muse/avatar.webp) | ![Wed](01-main-avatar/03-purple-pearl-dress/muse/avatar.webp) | ![Thu](01-main-avatar/04-red-hanfu/muse/avatar.webp) |

| Fri · Light blue suit | Sat · White hanfu | Sun · Pink sweater | Spare · Mint qipao |
|---|---|---|---|
| ![Fri](01-main-avatar/05-light-blue-suit/muse/avatar.webp) | ![Sat](01-main-avatar/06-white-hanfu/muse/avatar.webp) | ![Sun](01-main-avatar/07-pink-sweater/muse/avatar.webp) | ![Spare](01-main-avatar/08-mint-qipao/muse/avatar.webp) |

### 02 · Lin Yiyi & 03 · Twin-tails

| Lin Yiyi | Twin-tails |
|---|---|
| ![Lin Yiyi](02-lin-yiyi/muse/avatar.webp) | ![Twin-tails](03-twin-tails/muse/avatar.webp) |

## Repository layout

```
.
├── README.md / README.zh-CN.md   # this page
├── TUTORIAL.md / TUTORIAL.zh-CN.md
│                                 # how to turn any look into a Codex pet
├── 01-main-avatar/               # one numbered folder per character
│   ├── README.md                 # character overview
│   ├── 01-pink-hanfu/            # one folder per outfit, each with:
│   │   ├── README.md             #   outfit overview
│   │   ├── muse/                 #   Muse avatar assets (+ README)
│   │   └── codex/                #   Codex pet package or plan (+ README)
│   ├── 02-teal-hanfu/
│   ├── ...
│   └── 08-mint-qipao/
├── 02-lin-yiyi/                  # single-look characters keep the same
│   ├── muse/                     # inner layout directly (README + muse/
│   └── codex/                    # + codex/)
└── 03-twin-tails/
```

## The Codex pet

So far only the **pink hanfu** outfit has a pet: a Codex Pet v2 package
redrawn frame by frame (8 columns × 11 rows, 1536×2288). Full spec,
previews and install guide:
[`01-main-avatar/01-pink-hanfu/codex/`](01-main-avatar/01-pink-hanfu/codex/).

![Codex sprite sheet](01-main-avatar/01-pink-hanfu/codex/preview/contact-sheet.png)

| idle | waving | working | jumping |
|---|---|---|---|
| ![idle](01-main-avatar/01-pink-hanfu/codex/preview/idle.gif) | ![waving](01-main-avatar/01-pink-hanfu/codex/preview/waving.gif) | ![working](01-main-avatar/01-pink-hanfu/codex/preview/working.gif) | ![jumping](01-main-avatar/01-pink-hanfu/codex/preview/jumping.gif) |

**Install**: copy `01-main-avatar/01-pink-hanfu/codex/pink-hanfu/` into
`~/.codex/pets/` (Windows: `%USERPROFILE%\.codex\pets\`), then in the
ChatGPT / Codex desktop app go to **Settings → Pets → Refresh** and select
**"粉白古装 · Pink Hanfu"**.

Want a pet for another look? Follow [**TUTORIAL.md**](TUTORIAL.md) —
the full pipeline, with a suggested pet id per look.

## Disclaimer

Personal, non-commercial works. The characters are stylized cartoon
depictions, unrelated to any real person or to OpenAI, Meta, or any other
company. Please do not use commercially. Character 02 (Lin Yiyi) is a fan
work; see its own folder for details.
