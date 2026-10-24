# 第2期备料清单 · `2026-10-22_downloads-organize`

状态：**冷启动已跑通**：2026-10-24（Asia/Shanghai）真 key、干净会话、只给一句「照这个仓库复现第2期 file://<副本>」，`dsh headless` 实跑，产出由 DSH 的 write/edit 工具写，结构对 `sample/`、原件 `cmp` 一致。本次提交推送（commit 见 `git log`）。
远端：`AKA-qinnashou/qinnashou-dsh-cases`。

## 文件清单

| 路径 | 用途 |
|---|---|
| `demo-下载/`（51 个） | 虚构输入：占位文件，名字照截图 07/08 |
| `sample/{文档,图片,压缩包,安装包,表格,其他}/`（51 个） | 示例产出：DSH 实跑归类后的占位文件 |
| `MANIFEST.md` | 本清单 |
| `README.md` | 场景/输入/输出/三平台用法 + 复现（给 agent）/人工步骤/验收 |
| `doubao/工作任务配置.md` | 豆包：豆包工作·本地电脑步骤 |
| `dsh/AGENTS.md` | DSH：工作区规矩（headless 靠它） |
| `dsh/downloads-organize.patch.yml` | DSH：--patch 预设（只对 dsh web/桌面端有效，headless 不生效） |
| `prompt.md` | 通用层：提示词原文 |
| `sample/整理报告.md` | 示例产出 |
| `screenshots/01_整理前乱文件夹实拍.png` | 演示截图 |
| `screenshots/01_整理前列表.png` | 演示截图 |
| `screenshots/01_整理前列表_文字版.png` | 演示截图 |
| `screenshots/02_官网Harness下载页.png` | 演示截图 |
| `screenshots/03_WebUI主界面.png` | 演示截图 |
| `screenshots/04_粘贴提示词.png` | 演示截图 |
| `screenshots/05_整理过程.png` | 演示截图 |
| `screenshots/06_整理后子文件夹.png` | 演示截图 |
| `screenshots/07_搬移清单.png` | 演示截图 |
| `screenshots/08_整理后清单树.png` | 演示截图 |
| `screenshots/09_前后对比.png` | 演示截图 |
| `trae/.trae/rules/downloads-organize.md` | Trae：规则文件 |
| `trae/智能体配置.md` | Trae：自定义智能体填表 |
| `分类规则.md` | 通用层：扩展名→子文件夹 |

## 待核

1. Trae 规则手写 `alwaysApply: true` 是否被识别——待核。
2. 本流程 Trae 是否实测——待核（未实测）。
3. 豆包「本地电脑」能否稳定读本地文件并写出产出——待核。
4. 豆包个人免费/订阅能否用「本地电脑」——待核。
5. 豆包「创建智能体」下线仅有第三方报道——待核。
6. 模型角标（DeepSeek-V41-Flash 等）对外口径——待核。
7. Trae「文件系统」工具能否直接移动文件——待核；终端 mv 可兜底。
8. `分类规则.md` 中 .7z .pkg .xls .doc .ppt 为按同类补的扩展名——待核。
9. 占位文件只有文字内容、扩展名是假的，真文件（二进制）下的归类未实测——待核。

## 示例数据说明

- `demo-下载/` 51 个文件是文字占位，扩展名照演示，内容不是真文件。
- `sample/` 来自 DSH 实跑。
- 密钥一律 `YOUR_API_KEY`。
