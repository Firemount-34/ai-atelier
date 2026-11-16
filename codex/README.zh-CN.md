# codex/ — Codex 智能伙伴（Pet）

**[English](README.md) | 中文**

Codex Pet v2 导入包，角色与仓库中的头像是同一个形象，穿周一服装，
全部帧为逐帧重绘。

## 安装

把 `pink-hanfu/` 整个文件夹复制到：

- macOS / Linux：`~/.codex/pets/pink-hanfu/`
- Windows：`%USERPROFILE%\.codex\pets\pink-hanfu\`
- 设置了 `CODEX_HOME` 时：`$CODEX_HOME/pets/pink-hanfu/`

文件夹内必须直接包含 `pet.json` 和 `spritesheet.webp` 两个文件
（不要多套一层文件夹）。然后打开 ChatGPT / Codex 桌面版 →
Settings → Pets → Refresh，选择「粉白古装 · Pink Hanfu」。

## 文件

| 路径 | 说明 |
|---|---|
| `pink-hanfu/pet.json` | 清单：id / displayName / description / spriteVersionNumber 2 / spritesheetPath |
| `pink-hanfu/spritesheet.webp` | 图集：1536×2288，8×11，每格 192×208，透明底，约 1.7 MB |
| `preview/contact-sheet.png` | 全图集预览 |
| `preview/*.gif` | idle / waving / working / jumping 动图预览 |
| `TUTORIAL.zh-CN.md` | 给其他服装做伙伴的教程 |

规格与逐行说明见仓库根目录的 [README](../README.zh-CN.md)。

## 给其他服装做伙伴

本仓库现成的伙伴只有周一服装这一只。其余七套服装在
[`../muse/outfits/`](../muse/)，想给哪套做伙伴就照着
[**TUTORIAL.zh-CN.md**](TUTORIAL.zh-CN.md) 做：里面是这只伙伴实际用过的
全流程——逐帧绘制 11 组动作条、切帧清理、拼装 1536×2288 图集、写
`pet.json`、校验、安装——并给每套服装都建议了一个宠物 id。
