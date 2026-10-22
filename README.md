# DSH 实践案例（秦拿手）

这个仓放公号里跑过的 DeepSeek Harness（DSH）实践。
一篇实践一个子目录。提示词、配置、截图、示例数据都在对应目录里。

同一套做法也能在 Trae、豆包上跑；每个子目录里 `dsh/`、`trae/`、`doubao/` 分开写。

## 案例索引

| 目录 | 说啥 | 对应公号 |
|---|---|---|
| [`2026-10-21_bill-audit/`](2026-10-21_bill-audit/) | 信用卡账单：揪刷错卡、漏领权益 | 第1期 |
| [`2026-10-22_downloads-organize/`](2026-10-22_downloads-organize/) | 下载文件夹：按类型只搬不删 | 第2期 |

## 每个子目录大概长这样

- `prompt.md`：提示词原文（通用）
- 示例输入（如有）：脱敏/虚构，README 里会写明
- `dsh/`：AGENTS.md + YAML patch（`--patch` + `insert`）
- `trae/`：`.trae/rules/` + 智能体配置说明
- `doubao/`：豆包工作 · 本地电脑步骤
- `screenshots/`：演示截图
- `README.md`：场景、输入、输出、三平台怎么用

## 注意

- 密钥一律写 `YOUR_API_KEY`，别把真钥匙写进仓。
- 账单类示例都是虚构数据，不是真实账单。
- 建仓、推送前先看根目录 `FILE_LIST.md`，交确认后再动远端。
