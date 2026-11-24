# AI Atelier — Virtual Avatars & Codex Pets

**English | [中文](README.zh-CN.md)**

> The workshop of **AI造物局** (AI Atelier): a collection of big-head chibi
> avatar looks. Traditional Chinese outfits are grouped into one series
> folder; every other look has its own numbered folder. Inside each look:
> `muse/` holds the Muse avatar assets, `codex/` holds the Codex desktop
> pet (built, or planned with a suggested pet id).

## Hanfu & Qipao series

| 01 · Pink hanfu | 02 · Teal hanfu | 03 · Red hanfu | 04 · White hanfu | 05 · Mint qipao |
|---|---|---|---|---|
| ![01](01-hanfu-qipao/01-pink-hanfu/muse/avatar.webp) | ![02](01-hanfu-qipao/02-teal-hanfu/muse/avatar.webp) | ![03](01-hanfu-qipao/03-red-hanfu/muse/avatar.webp) | ![04](01-hanfu-qipao/04-white-hanfu/muse/avatar.webp) | ![05](01-hanfu-qipao/05-mint-qipao/muse/avatar.webp) |

## Other looks

| 02 · Purple pearl dress | 03 · Light blue suit | 04 · Pink sweater | 05 · Lin Yiyi | 06 · Twin-tails |
|---|---|---|---|---|
| ![02](02-purple-pearl-dress/muse/avatar.webp) | ![03](03-light-blue-suit/muse/avatar.webp) | ![04](04-pink-sweater/muse/avatar.webp) | ![05](05-lin-yiyi/muse/avatar.webp) | ![06](06-twin-tails/muse/avatar.webp) |

| # | Folder | Contents | Codex pet |
|---|---|---|---|
| 01 | [Hanfu & Qipao series](01-hanfu-qipao/) · 汉服旗袍系列 | 5 traditional looks: pink hanfu (Mon), teal hanfu (Tue), red hanfu (Thu), white hanfu (Sat), mint qipao (spare) | ✅ pink hanfu built, rest planned |
| 02 | [Purple pearl dress](02-purple-pearl-dress/) · 紫色珍珠礼服 | Wednesday of the weekly rotation | planned |
| 03 | [Light blue suit](03-light-blue-suit/) · 浅蓝西装现代装 | Friday | planned |
| 04 | [Pink sweater](04-pink-sweater/) · 粉色毛衣日常装 | Sunday | planned |
| 05 | [Lin Yiyi](05-lin-yiyi/) · 林一一 | Q-version Lin Yiyi from the Douyin drama 《我的妹妹不可爱》; Muse avatar since 2026-11-20 | planned |
| 06 | [Twin-tails](06-twin-tails/) · 原创双马尾 | Fully original pixel-art chibi girl | planned |

The weekly rotation (Mon–Sun) is one character in seven outfits — big-head,
upper-body, typing on a small laptop — plus the spare qipao. Looks 05 and 06
are separate characters in a pixel-art chibi style.

## Repository layout

```
.
├── README.md / README.zh-CN.md   # this page
├── TUTORIAL.md / TUTORIAL.zh-CN.md
│                                 # how to turn any look into a Codex pet
├── 01-hanfu-qipao/               # the Hanfu & Qipao series
│   ├── README.md                 # series overview
│   ├── 01-pink-hanfu/            # one folder per look, each with:
│   │   ├── README.md             #   look overview
│   │   ├── muse/                 #   Muse avatar assets (+ README)
│   │   └── codex/                #   Codex pet package or plan (+ README)
│   ├── 02-teal-hanfu/
│   ├── ...
│   └── 05-mint-qipao/
├── 02-purple-pearl-dress/        # standalone looks, same inner layout
├── ...
└── 06-twin-tails/
```

## The Codex pet

So far only the **pink hanfu** look has a pet: a Codex Pet v2 package
redrawn frame by frame (8 columns × 11 rows, 1536×2288). Full spec,
previews and install guide:
[`01-hanfu-qipao/01-pink-hanfu/codex/`](01-hanfu-qipao/01-pink-hanfu/codex/).

![Codex sprite sheet](01-hanfu-qipao/01-pink-hanfu/codex/preview/contact-sheet.png)

| idle | waving | working | jumping |
|---|---|---|---|
| ![idle](01-hanfu-qipao/01-pink-hanfu/codex/preview/idle.gif) | ![waving](01-hanfu-qipao/01-pink-hanfu/codex/preview/waving.gif) | ![working](01-hanfu-qipao/01-pink-hanfu/codex/preview/working.gif) | ![jumping](01-hanfu-qipao/01-pink-hanfu/codex/preview/jumping.gif) |

**Install**: copy `01-hanfu-qipao/01-pink-hanfu/codex/pink-hanfu/` into
`~/.codex/pets/` (Windows: `%USERPROFILE%\.codex\pets\`), then in the
ChatGPT / Codex desktop app go to **Settings → Pets → Refresh** and select
**"粉白古装 · Pink Hanfu"**.

Want a pet for another look? Follow [**TUTORIAL.md**](TUTORIAL.md) —
the full pipeline, with a suggested pet id per look.

## Disclaimer

Personal, non-commercial works. The characters are stylized cartoon
depictions, unrelated to any real person or to OpenAI, Meta, or any other
company. Please do not use commercially. Character 05 (Lin Yiyi) is a fan
work; see its own folder for details.
