# 第4期备料清单 · `2026-10-25_resume-jd`

状态：正文在 `4b9ede6`，复现补丁（仓根 `AGENTS.md` 等）已在 `548effb` 推送。冷启动已跑通：2026-10-24（Asia/Shanghai）真 key、干净会话、`dsh headless` 实跑，结构对 `sample/`、原件逐字节一致；仓根索引覆盖 1–4 期后又重跑一次，同样跑通，本次提交推送。
远端：`AKA-qinnashou/qinnashou-dsh-cases`。早先的 `6a8f3b0` 不合格，`4b9ede6` 在它之上补齐、取代了它的内容。
生成时间：2026-10-24（Asia/Shanghai）。

## 文件清单

| 路径 | 用途 |
|---|---|
| `README.md` | 场景/输入/输出/三平台用法（可复现） |
| `demo-JD-云杉教育-用户增长.md` | 虚构示例输入：JD |
| `demo-JD-星河电商-内容运营.md` | 虚构示例输入：JD |
| `demo-JD-麦田咖啡-品牌策划.md` | 虚构示例输入：JD |
| `demo-简历-原件.md` | 虚构示例输入：原简历 |
| `doubao/工作任务配置.md` | 豆包：豆包工作·本地电脑步骤 |
| `dsh/AGENTS.md` | DSH：工作区规矩 |
| `dsh/resume-jd.patch.yml` | DSH：--patch 预设（insert 写法，dump-config 已过） |
| `prompt.md` | 通用层：提示词原文（一字不改自 draft-final） |
| `sample/gaps/待补清单.md` | 示例：待补清单 |
| `sample/match/01-云杉教育-用户增长专员.md` | 示例：每岗匹配说明 |
| `sample/match/02-星河电商-内容运营.md` | 示例：每岗匹配说明 |
| `sample/match/03-麦田咖啡-品牌策划.md` | 示例：每岗匹配说明 |
| `sample/raw/JD-云杉教育-用户增长.md` | 示例：跑后归位的原件 |
| `sample/raw/JD-星河电商-内容运营.md` | 示例：跑后归位的原件 |
| `sample/raw/JD-麦田咖啡-品牌策划.md` | 示例：跑后归位的原件 |
| `sample/raw/简历-原件.md` | 示例：跑后归位的原件 |
| `sample/tailored/林小满-云杉教育-用户增长专员.md` | 示例：每岗对口版简历 |
| `sample/tailored/林小满-星河电商-内容运营.md` | 示例：每岗对口版简历 |
| `sample/tailored/林小满-麦田咖啡-品牌策划.md` | 示例：每岗对口版简历 |
| `sample/已确认经历清单.md` | 示例：已确认经历清单 |
| `screenshots/S1_工作区.png` | 演示：DSH 工作区 |
| `screenshots/S2_简历与JD入夹.png` | 演示：简历与 JD 入夹 |
| `screenshots/S3_粘贴提示词.png` | 演示：贴提示词 |
| `screenshots/S4_处理中.png` | 演示：处理中 |
| `screenshots/S5_跑完界面.png` | 演示：跑完（2分49秒） |
| `screenshots/S6_待补清单.png` | 演示：待补清单 |
| `trae/.trae/rules/resume-jd.md` | Trae：规则文件 |
| `trae/智能体配置.md` | Trae：自定义智能体填表 |
| `改写判据.md` | 通用层：已覆盖/可改写对齐/缺口/待确认判据 |
| `MANIFEST.md` | 本清单 |

## 待核

1. Trae 规则手写 `alwaysApply: true` 是否被识别——待核。依据：https://docs.trae.cn/ide_rules
2. Trae 读 pdf/docx 简历是否稳定、本流程是否实测——待核（未实测）。依据：https://docs.trae.cn/ide_agent
3. 豆包「本地电脑」能否稳定读 md/pdf/docx 并写出 tailored/gaps——待核。依据：https://www.doubao.com/work/docs/zh-cn/articles/705018132598-plugins.md
4. 豆包个人免费/个人订阅能否用「本地电脑」——待核。依据：同上 + https://www.doubao.com/work/docs/zh-cn/articles/998584058135-projects.md
5. 豆包工作伙伴表单除「指令」外字段名——待核。依据：https://www.doubao.com/work/docs/zh-cn/articles/559204524686-workmates.md
6. 豆包「创建智能体」下线仅有第三方报道——待核。依据：https://www.sohu.com/a/1045721026_313745
7. 模型角标 DeepSeek-V41-Flash High 对外口径——待核（沿用第1期）。依据：screenshots/S1、S5 界面
8. 未补第四个平台：本轮未取得足够官方文档依据——待核。
9. （已解决）复现补丁已在 `548effb` 推送。

## 示例数据说明

- 简历、JD、`sample/**` 全部虚构（人名、公司、电话 138-0000-0000、邮箱 example.com、数字）。README 已声明。
- 截图为 DSH 界面，内容为同一虚构样本；未见 API key 明文。
- 密钥一律 `YOUR_API_KEY`。

## 禁做（本轮已遵守）

推送只走普通 commit + `git push origin main`，无 force。未放公号正文、公号配图。
