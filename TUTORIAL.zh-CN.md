# 教程：把一张头像图做成 Codex 智能伙伴

**[English](TUTORIAL.md) | 中文**

这就是本仓库 `pink-hanfu` 伙伴的实际制作流程。拿本仓库里任意一个形象文件夹
中那套服装的形象图照着做，就能得到那套服装对应的伙伴——除了拼装那一步
要跑一个小 Python 脚本，不需要其他编程基础。

## 你要做出来的东西

Codex 伙伴就是一个普通文件夹，里面只有两个文件：

```
<宠物id>/
├── pet.json
└── spritesheet.webp
```

| 要求 | 值 |
|---|---|
| 格式 | Codex Pet v2（pet.json 里 `"spriteVersionNumber": 2`） |
| 图集尺寸 | 1536 × 2288 px，8 列 × 11 行 |
| 单格 | 192 × 208 px，透明背景，WebP 或 PNG |
| 文件大小 | 小于 20 MiB |
| 安装位置 | `~/.codex/pets/<宠物id>/`（Windows：`%USERPROFILE%\.codex\pets\<宠物id>\`） |

## 第 1 步 — 准备源图

从一张干净的角色图开始：大头卡通、上半身、浅色纯背景、穿着你想要的那套服装。
每个形象文件夹里的 `muse/avatar.webp`（1600 × 1600）正是这种图。整个绘制过程都要把这张图
开着当参照——脸、发型、服装细节在每一帧之间都不能漂移。

## 第 2 步 — 逐帧绘制 11 组动作条

**不要**拿一张图做位移/缩放凑动画，效果会很廉价。正确做法是每个动画行画一条
横向长条，帧数必须和下表一致，用源图作为图像生成工具的角色参照。

| 行 | 状态 | 帧数 | 画什么 |
|---|---|---|---|
| 0 | idle 待机 | 6 | 轻微呼吸起伏、眨一次眼；保持敲电脑姿势 |
| 1 | running-right | 8 | 向右奔跑，头发和衣袖向后飘 |
| 2 | running-left | 8 | 向左奔跑——可以直接镜像第 1 行（规格允许） |
| 3 | waving 挥手 | 4 | 举起一只手挥手打招呼 |
| 4 | jumping 跳跃 | 5 | 下蹲 → 起跳 → 腾空 → 下落 → 落地 |
| 5 | failed 失败 | 8 | 愣住 → 垂头 → 趴在键盘上 |
| 6 | waiting 等待 | 6 | 东张西望、托腮、招手催促 |
| 7 | running（工作） | 6 | 专注敲键盘，双手交替 |
| 8 | review 检查 | 6 | 凑近检查、点头、竖大拇指 |
| 9 | 看向方向 A | 8 | 视线：上、右上、右、右下、下、左下、左、左上——头和眼睛顺时针转 |
| 10 | 看向方向 B | 8 | 同样 8 个方向，按 22.5° 步进补齐（22.5°、67.5°、…、337.5°） |

效果不错的提示词模板：

> "Sprite strip of exactly N frames in a row, same big-head chibi girl as the
> reference image, same face, hairstyle and outfit, [动作描述],
> evenly spaced, plain white background, consistent character size in every frame"

粉白古装那次的经验：

- **每条长条回来都要数帧数。** 有一条看向方向的长条只画了 7 帧而不是 8 帧，
  缺的 337.5° 那一帧是单独补画一张再插进去的。
- 让画面间距留宽一点——奔跑这类宽姿势间距太紧会和邻帧重叠，切帧时很麻烦。
- 第 1 行（向右跑）画好就行，第 2 行直接镜像。

## 第 3 步 — 切帧并清理

把每条长条切成单帧，去掉背景让每帧透明（源图是纯色背景，用边缘连通去除
效果很好）。如果姿势比长条间距宽，等分切会切到脸——改用连通域提取单帧，
粘连的一对在投影谷值处分开。之后放大检查每帧边缘，擦掉邻帧的残片；
细如发丝的一点残留可以接受，明显的块不行。

所有帧缩放到能放进 192 × 208 的格子，全表保持统一的角色大小和基线。

## 第 4 步 — 拼装图集

把帧按行序放到 1536 × 2288 的透明画布上，每行 8 格。有两个格子特殊：

- 第 0 行第 6 列：**中立正视姿势**（复用 idle 第 1 帧即可）
- 第 0 行第 7 列以及其他所有未用格：**完全透明**——校验器会拒绝那里的杂散像素

拼装脚本示例（Python + Pillow）：

```python
from PIL import Image

CELL_W, CELL_H, COLS = 192, 208, 8
sheet = Image.new("RGBA", (1536, 2288), (0, 0, 0, 0))
# frames[row] = 该行的 RGBA 帧图列表，已缩放到格子大小
for row, row_frames in enumerate(frames):
    for col, frame in enumerate(row_frames):
        sheet.alpha_composite(frame, (col * CELL_W, row * CELL_H))
sheet.save("spritesheet.webp", lossless=True)
```

## 第 5 步 — 写 pet.json

```json
{
  "id": "teal-hanfu",
  "displayName": "Teal Hanfu",
  "description": "A big-head chibi cartoon girl with long black hair in a teal hanfu, typing on a small laptop. Every frame individually redrawn.",
  "spriteVersionNumber": 2,
  "spritesheetPath": "spritesheet.webp"
}
```

`id` 必须和文件夹名一致。每套服装建议用一个 id：

| 服装图 | 建议宠物 id |
|---|---|
| `01-hanfu-qipao/01-pink-hanfu/muse/avatar.webp`（周一） | `pink-hanfu` ✅ 已做好 |
| `01-hanfu-qipao/02-teal-hanfu/muse/avatar.webp`（周二） | `teal-hanfu` |
| `02-purple-pearl-dress/muse/avatar.webp`（周三） | `purple-pearl-dress` |
| `01-hanfu-qipao/03-red-hanfu/muse/avatar.webp`（周四） | `red-hanfu` |
| `03-light-blue-suit/muse/avatar.webp`（周五） | `light-blue-suit` |
| `01-hanfu-qipao/04-white-hanfu/muse/avatar.webp`（周六） | `white-hanfu` |
| `04-pink-sweater/muse/avatar.webp`（周日） | `pink-sweater` |
| `01-hanfu-qipao/05-mint-qipao/muse/avatar.webp`（备用） | `mint-qipao` |

## 第 6 步 — 安装前校验

- [ ] 图集恰好 1536 × 2288，透明背景
- [ ] 每个应有帧格都有图；每个未用格 100% 透明
- [ ] 每行帧数与第 2 步表格一致（共 74 个有图格 + 中立格）
- [ ] `pet.json` 能解析，`spriteVersionNumber` 为 2，`id` 与文件夹名一致
- [ ] 总大小小于 20 MiB

## 第 7 步 — 安装

把成品文件夹复制进 pets 目录，然后在 ChatGPT / Codex 桌面版里打开
**Settings → Pets → Refresh**，选中你的伙伴，用 `/pet` 唤醒或收起。
每套服装重复一遍即可——不同 id 的伙伴可以并存，整个衣柜集齐后随时切换。
