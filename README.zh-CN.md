# AI Atelier — 虚拟形象与 Codex 宠物

**[English](README.md) | 中文**

> **AI造物局**的工坊：大头 Q 版虚拟形象合集。每个形象住在一个带序号的
> 文件夹里，按平台分二级目录——`muse/` 放 Muse 头像素材，`codex/` 放
> Codex 桌面宠物（已做好的，或计划中并附建议宠物 id）。

## 形象一览

| 01 · 粉白古装 | 02 · 青绿古装 | 03 · 紫色珍珠礼服 | 04 · 红色金纹古装 | 05 · 浅蓝西装 |
|---|---|---|---|---|
| ![01](01-pink-hanfu/muse/avatar.webp) | ![02](02-teal-hanfu/muse/avatar.webp) | ![03](03-purple-pearl-dress/muse/avatar.webp) | ![04](04-red-hanfu/muse/avatar.webp) | ![05](05-light-blue-suit/muse/avatar.webp) |

| 06 · 白衣古装 | 07 · 粉色毛衣 | 08 · 薄荷绿旗袍 | 09 · 林一一 | 10 · 原创双马尾 |
|---|---|---|---|---|
| ![06](06-white-hanfu/muse/avatar.webp) | ![07](07-pink-sweater/muse/avatar.webp) | ![08](08-mint-qipao/muse/avatar.webp) | ![09](09-lin-yiyi/muse/avatar.webp) | ![10](10-twin-tails/muse/avatar.webp) |

| # | 形象 | 说明 | Codex 宠物 |
|---|---|---|---|
| 01 | [粉白刺绣古装](01-pink-hanfu/) · Pink hanfu | 每周轮换的周一造型；最初的主头像 | ✅ 已做好 |
| 02 | [青绿古装](02-teal-hanfu/) · Teal hanfu | 周二 | 计划中 |
| 03 | [紫色珍珠礼服](03-purple-pearl-dress/) · Purple pearl dress | 周三 | 计划中 |
| 04 | [红色金纹古装](04-red-hanfu/) · Red hanfu | 周四 | 计划中 |
| 05 | [浅蓝西装现代装](05-light-blue-suit/) · Light blue suit | 周五 | 计划中 |
| 06 | [白衣仙气古装](06-white-hanfu/) · White hanfu | 周六 | 计划中 |
| 07 | [粉色毛衣日常装](07-pink-sweater/) · Pink sweater | 周日 | 计划中 |
| 08 | [薄荷绿旗袍](08-mint-qipao/) · Mint qipao | 备用造型 | 计划中 |
| 09 | [林一一](09-lin-yiyi/) · Lin Yiyi | Q版林一一，抖音短剧《我的妹妹不可爱》角色；2026-11-20 起担任 Muse 头像 | 计划中 |
| 10 | [原创双马尾](10-twin-tails/) · Twin-tails | 完全原创的像素风大头 Q 版女孩 | 计划中 |

01–08 是同一个形象的八套造型——大头、上半身、敲电脑——作为 Muse
助手的头像每周轮换。09 和 10 是像素风 Q 版的独立造型。

## 仓库结构

```
.
├── README.md / README.zh-CN.md   # 本页
├── TUTORIAL.md / TUTORIAL.zh-CN.md
│                                 # 把任何形象做成 Codex 宠物的教程
├── 01-pink-hanfu/                # 每个形象一个带序号的文件夹
│   ├── README.md                 # 形象总览
│   ├── muse/                     # Muse 头像素材（+ README）
│   └── codex/                    # Codex 宠物包或计划（+ README）
├── 02-teal-hanfu/
├── ...
└── 10-twin-tails/
```

## Codex 宠物

目前只有 **01 · 粉白古装** 有宠物：一只逐帧重绘的 Codex Pet v2
（8 列 × 11 行，1536×2288）。完整规格、预览和安装说明见
[`01-pink-hanfu/codex/`](01-pink-hanfu/codex/)。

![Codex 精灵图](01-pink-hanfu/codex/preview/contact-sheet.png)

| 空闲 | 挥手 | 工作 | 跳跃 |
|---|---|---|---|
| ![idle](01-pink-hanfu/codex/preview/idle.gif) | ![waving](01-pink-hanfu/codex/preview/waving.gif) | ![working](01-pink-hanfu/codex/preview/working.gif) | ![jumping](01-pink-hanfu/codex/preview/jumping.gif) |

**安装**：把 `01-pink-hanfu/codex/pink-hanfu/` 复制到 `~/.codex/pets/`
（Windows：`%USERPROFILE%\.codex\pets\`），然后在 ChatGPT / Codex
桌面端打开 **设置 → Pets → Refresh**，选择「粉白古装 · Pink Hanfu」。

想给其他形象做宠物？看 [**TUTORIAL.zh-CN.md**](TUTORIAL.zh-CN.md)
——完整流程，并附每个形象建议的宠物 id。

## 说明

个人非商业作品。角色均为风格化卡通形象，与任何真人以及 OpenAI、
Meta 等任何公司无关，请勿商用。09 号形象是同人作品，细节见其文件夹。
