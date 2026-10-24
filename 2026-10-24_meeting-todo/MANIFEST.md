# 第3期备料清单 · `2026-10-24_meeting-todo`

状态：**冷启动已跑通**：2026-10-24（Asia/Shanghai）真 key、干净会话、只给一句「照这个仓库复现第3期 file://<副本>」，`dsh headless` 实跑，产出由 DSH 的 write/edit 工具写，结构对 `sample/`、原件 `cmp` 一致。本次提交推送（commit 见 `git log`）。
公开仓（已存在、已关联）：`AKA-qinnashou/qinnashou-dsh-cases`（远端 `origin` → `https://github.com/AKA-qinnashou/qinnashou-dsh-cases.git`）。
本期正文早已在远端（`548effb` 之前）；本次补「复现（给 agent）」「人工步骤」「验收」。

生成时间：2026-10-23（Asia/Shanghai）；2026-10-24 更新。

---

## 文件清单

| 路径 | 用途 |
|---|---|
| `README.md` | 场景/输入/输出/三平台用法（可复现） |
| `prompt.md` | 提示词原文（一字不改自 draft-final 第三节） |
| `优先级判据.md` | 通用层：高/中/低/待确认判据 |
| `demo-input-1.md` | 虚构示例纪要（双十一运营周会） |
| `demo-input-2.md` | 虚构示例纪要（新员工入职流程） |
| `sample/meetings/raw/demo-input-1.md` | 示例：跑前 raw 原件 |
| `sample/meetings/raw/demo-input-2.md` | 示例：跑前 raw 原件 |
| `sample/meetings/summaries/demo-input-1.md` | 示例：跑后摘要 |
| `sample/meetings/summaries/demo-input-2.md` | 示例：跑后摘要 |
| `sample/tasks/今日待办.md` | 示例：跑后今日待办（16 条） |
| `dsh/AGENTS.md` | DSH 工作区规矩 |
| `dsh/meeting-todo.patch.yml` | DSH `--patch` 预设（insert 写法） |
| `trae/.trae/rules/meeting-todo.md` | Trae 规则文件 |
| `trae/智能体配置.md` | Trae 自定义智能体填表说明 |
| `doubao/工作任务配置.md` | 豆包工作·本地电脑步骤 |
| `screenshots/S1_工作区.png` | 演示：选工作区 |
| `screenshots/S2_飞书妙记导出.png` | 演示：飞书导出文字记录 |
| `screenshots/S3_腾讯会议纪要.png` | 演示：腾讯会议纪要复制 |
| `screenshots/S4_粘贴提示词.png` | 演示：贴提示词 |
| `screenshots/S5_处理中.png` | 演示：处理中 |
| `screenshots/S6b_跑完界面.png` | 演示：跑完（16 条 / 1分51秒） |
| `screenshots/S7_待确认栏.png` | 演示：待确认栏 |
| `screenshots/配图_workflow-16x9.png` | 公号配图：工作流（非操作步骤） |
| `screenshots/配图_mascot-spot-16x9.png` | 公号配图：奶油球场景图（非操作步骤；正文不写点缀/Designer 元说明） |
| `MANIFEST.md` | 本清单 |

---

## 【待核】

查不到或不确的，标在这里，**未编造**。确认前勿当定论写进对外文案。

1. **飞书妙记**：个别企业版「导出文字记录」菜单名是否与正文一致——待核（正文已标【待核实】）。
2. **腾讯会议**：当前客户端是否已灰度「复制为 Markdown」；智能录制/纪要最低版本号——待核（正文未写死版本）。
3. **腾讯会议**「文字转写」导出属付费能力的版本边界（专业/商业/企业/教育）——待核（正文已提示免费用户别死磕）。
4. **Trae** 规则手写 `alwaysApply: true` 是否被识别——待核（沿用第1–2期）。
5. **Trae** 本流程（会议纪要→今日待办）是否实测——待核（未实测）。
6. **豆包**「本地电脑」能否稳定读 md、建夹并写出 summaries/tasks——待核。
7. **豆包**个人免费/个人订阅能否用「本地电脑」——待核。
8. **豆包**工作伙伴「创建新伙伴」除「指令」外的表单字段名——待核。
9. **豆包**原「创建智能体」下线依据为第三方报道（2026-07-15），非官方公告页——待核（是否改 README 措辞）。
10. **模型角标** DeepSeek-V41-Flash High 对外是否统一口径——待核（沿用第1期待核）。
11. **S1 截图**：实测在已进入工作区目录内启动，未再弹出「选择工作区目录」对话框——缺该步独立截图是否要补——待核（见源 `实测结果.md`）。
12. `sample/` 是否为当初演示 DSH 原样产出——待核（冷启动实跑结构与之一致）。

---

## 示例数据说明

- `demo-input-*.md`、`sample/**`：源材料已标明「演示用虚构样本」；人名、公司、数字均为编造。
- README 再次声明「虚构 / 脱敏」；禁真会议隐私、真密钥。
- 截图中可见事项与样例一致；未见 API key 明文。

## 禁做事项（本轮已遵守）

- 未 `gh repo create`；推送只走一次普通 commit + `git push origin main`，无 force。
- 未写入真 API key；文案统一 `YOUR_API_KEY`。
- 未把公号全文当作 README 唯一内容；未纳入内部备注、口播、真机隐私等非作品集必需文件。
