# AI Atelier — 虚拟形象与 Codex 宠物

**[English](README.md) | 中文**

> **AI造物局**的工坊：大头 Q 版虚拟形象合集。每个形象一个带序号的
> 文件夹；文件夹内每个造型按平台分二级目录——`muse/` 放 Muse
> 头像素材，`codex/` 放 Codex 桌面宠物（已做好的，或计划中并附
> 建议宠物 id）。

## 形象一览

| # | 形象 | 造型 | Codex 宠物 |
|---|---|---|---|
| 01 | [主形象](01-main-avatar/) · The Main Avatar | 同一个形象的 8 套造型，每周轮换（周一至周日 + 备用） | ✅ 粉白古装已做好，其余计划中 |
| 02 | [林一一](02-lin-yiyi/) · Lin Yiyi | Q版林一一，抖音短剧《我的妹妹不可爱》角色；2026-11-20 起担任 Muse 头像 | 计划中 |
| 03 | [原创双马尾](03-twin-tails/) · Twin-tails | 完全原创的像素风大头 Q 版女孩 | 计划中 |

### 01 · 主形象 — 8 套造型

| 周一 · 粉白古装 | 周二 · 青绿古装 | 周三 · 紫色珍珠礼服 | 周四 · 红色金纹古装 |
|---|---|---|---|
| ![Mon](01-main-avatar/01-pink-hanfu/muse/avatar.webp) | ![Tue](01-main-avatar/02-teal-hanfu/muse/avatar.webp) | ![Wed](01-main-avatar/03-purple-pearl-dress/muse/avatar.webp) | ![Thu](01-main-avatar/04-red-hanfu/muse/avatar.webp) |

| 周五 · 浅蓝西装 | 周六 · 白衣古装 | 周日 · 粉色毛衣 | 备用 · 薄荷绿旗袍 |
|---|---|---|---|
| ![Fri](01-main-avatar/05-light-blue-suit/muse/avatar.webp) | ![Sat](01-main-avatar/06-white-hanfu/muse/avatar.webp) | ![Sun](01-main-avatar/07-pink-sweater/muse/avatar.webp) | ![Spare](01-main-avatar/08-mint-qipao/muse/avatar.webp) |

### 02 · 林一一 & 03 · 原创双马尾

| 林一一 | 原创双马尾 |
|---|---|
| ![Lin Yiyi](02-lin-yiyi/muse/avatar.webp) | ![Twin-tails](03-twin-tails/muse/avatar.webp) |

## 仓库结构

```
.
├── README.md / README.zh-CN.md   # 本页
├── TUTORIAL.md / TUTORIAL.zh-CN.md
│                                 # 把任何造型做成 Codex 宠物的教程
├── 01-main-avatar/               # 每个形象一个带序号的文件夹
│   ├── README.md                 # 形象总览
│   ├── 01-pink-hanfu/            # 每个造型一个文件夹，内含：
│   │   ├── README.md             #   造型总览
│   │   ├── muse/                 #   Muse 头像素材（+ README）
│   │   └── codex/                #   Codex 宠物包或计划（+ README）
│   ├── 02-teal-hanfu/
│   ├── ...
│   └── 08-mint-qipao/
├── 02-lin-yiyi/                  # 单造型形象直接沿用同样的内部结构
│   ├── muse/                     # （README + muse/ + codex/）
│   └── codex/
└── 03-twin-tails/
```

## Codex 宠物

目前只有**粉白古装**有宠物：一只逐帧重绘的 Codex Pet v2
（8 列 × 11 行，1536×2288）。完整规格、预览和安装说明见
[`01-main-avatar/01-pink-hanfu/codex/`](01-main-avatar/01-pink-hanfu/codex/)。

![Codex 精灵图](01-main-avatar/01-pink-hanfu/codex/preview/contact-sheet.png)

| 空闲 | 挥手 | 工作 | 跳跃 |
|---|---|---|---|
| ![idle](01-main-avatar/01-pink-hanfu/codex/preview/idle.gif) | ![waving](01-main-avatar/01-pink-hanfu/codex/preview/waving.gif) | ![working](01-main-avatar/01-pink-hanfu/codex/preview/working.gif) | ![jumping](01-main-avatar/01-pink-hanfu/codex/preview/jumping.gif) |

**安装**：把 `01-main-avatar/01-pink-hanfu/codex/pink-hanfu/` 复制到
`~/.codex/pets/`（Windows：`%USERPROFILE%\.codex\pets\`），然后在
ChatGPT / Codex 桌面端打开 **设置 → Pets → Refresh**，
选择「粉白古装 · Pink Hanfu」。

想给其他造型做宠物？看 [**TUTORIAL.zh-CN.md**](TUTORIAL.zh-CN.md)
——完整流程，并附每个造型建议的宠物 id。

## 说明

个人非商业作品。角色均为风格化卡通形象，与任何真人以及 OpenAI、
Meta 等任何公司无关，请勿商用。02 号形象（林一一）是同人作品，
细节见其文件夹。
