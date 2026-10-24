# 第1期备料清单 · `2026-10-21_bill-audit`

状态：**冷启动已跑通**：2026-10-24（Asia/Shanghai）真 key、干净会话、只给一句「照这个仓库复现第1期 file://<副本>」，`dsh headless` 实跑，产出由 DSH 的 write/edit 工具写，结构对 `sample/`、原件 `cmp` 一致。本次提交推送（commit 见 `git log`）。
远端：`AKA-qinnashou/qinnashou-dsh-cases`。

## 文件清单

| 路径 | 用途 |
|---|---|
| `MANIFEST.md` | 本清单 |
| `README.md` | 场景/输入/输出/三平台用法 + 复现（给 agent）/人工步骤/验收 |
| `doubao/工作任务配置.md` | 豆包：豆包工作·本地电脑步骤 |
| `dsh/AGENTS.md` | DSH：工作区规矩（headless 靠它） |
| `dsh/bill-audit.patch.yml` | DSH：--patch 预设（只对 dsh web/桌面端有效，headless 不生效） |
| `prompt.md` | 通用层：提示词原文 |
| `sample/审计报告.md` | 示例产出 |
| `screenshots/01_界面.png` | 演示截图 |
| `screenshots/02_提问.png` | 演示截图 |
| `screenshots/03_读文件.png` | 演示截图 |
| `screenshots/04_刷错卡.png` | 演示截图 |
| `screenshots/05_漏领.png` | 演示截图 |
| `screenshots/06_汇总.png` | 演示截图 |
| `screenshots/07_关键假设与结论.png` | 演示截图 |
| `screenshots/install/01_官网下载页.png` | 装机截图 |
| `screenshots/install/02_桌面端打开.png` | 装机截图 |
| `screenshots/install/03_node版本.png` | 装机截图 |
| `screenshots/install/04_dsh-web启动.png` | 装机截图 |
| `screenshots/install/05_平台新建Key.png` | 装机截图 |
| `screenshots/install/06_设置填Key.png` | 装机截图 |
| `screenshots/install/07_选择工作区.png` | 装机截图 |
| `screenshots/install/08_样板两文件.png` | 装机截图 |
| `screenshots/install/11_文档首页.png` | 装机截图 |
| `trae/.trae/rules/bill-audit.md` | Trae：规则文件 |
| `trae/智能体配置.md` | Trae：自定义智能体填表 |
| `我的卡权益.md` | 虚构输入 |
| `账单.csv` | 虚构输入 |

## 待核

1. Trae 规则手写 `alwaysApply: true` 是否被识别——待核。
2. 本流程 Trae 是否实测——待核（未实测）。
3. 豆包「本地电脑」能否稳定读本地文件并写出产出——待核。
4. 豆包个人免费/订阅能否用「本地电脑」——待核。
5. 豆包「创建智能体」下线仅有第三方报道——待核。
6. 模型角标（DeepSeek-V41-Flash 等）对外口径——待核。
7. DeepSeek 开放平台「新建 Key」准确菜单名、是否需先充值——待核。
8. headless 实跑金额每次可能略有出入（演示 171.60，实跑 `sample/` 171.59），以手算抽查为准——候选。

## 示例数据说明

- `账单.csv`、`我的卡权益.md` 虚构：商户带「虚构」，卡尾号 8888/6666 编造，银行名示意。
- `sample/审计报告.md` 来自 DSH 实跑。
- 密钥一律 `YOUR_API_KEY`。
