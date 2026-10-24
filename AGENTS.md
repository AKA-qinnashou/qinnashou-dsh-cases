# 给 agent 看的入口

用户丢来这个仓、说「复现第 N 期」，它照下面走。

## 索引（1–4 期）

| 期 | 目录 | 产出（headless 下由 DSH 写） |
|---|---|---|
| 1 | `2026-10-21_bill-audit/` | `审计报告.md` |
| 2 | `2026-10-22_downloads-organize/` | 六个子文件夹 + `整理报告.md` |
| 3 | `2026-10-24_meeting-todo/` | `meetings/raw·summaries/` + `tasks/今日待办.md` |
| 4 | `2026-10-25_resume-jd/` | `已确认经历清单.md` + `raw/ match/ tailored/ gaps/` |

## 找期

第 N 期 = 根 `README.md`「案例索引」第 N 行的目录。进去先读该期 `README.md`「复现（给 agent）」一节。

## 通用流程

1. 克隆：用户给了仓库地址（含 `file://` 本地路径）就克隆那个地址，没给才用 `git clone https://github.com/AKA-qinnashou/qinnashou-dsh-cases.git`。一定先 `git clone` 再从克隆里取文件，不要直接读源路径。
2. 建空工作区（别在仓里跑）：`W=$(mktemp -d)`，按该期 README「复现」里的 `cp` 拷虚构样本进 `$W`（第1期拷 `账单.csv`+`我的卡权益.md`；第2期拷 `demo-下载/` 里的 51 个文件；第3期拷 `demo-input-*.md` 原名；第4期拷 `demo-*` 去掉前缀）。
3. 拷规矩：`cp <期目录>/dsh/AGENTS.md $W/`。
4. 装 DSH：`npm install -g @deepseek-ai/dsh`（没有全局写权限就加 `--prefix <可写目录>`，再用 `<prefix>/bin/dsh`）。实测 0.2.1-rc.2 在干净 npm 前缀下可装。
   - Node 要 ≥ 22.18（入口用 `import.meta.main`）。包里没写 `engines`，所以 npm 不会拦你。实测 Node 20.19 下 `dsh --version` 不报错、也没有任何输出；Node 22.21 正常。先 `node --version`；登录 shell 可能把 PATH 换回系统旧 Node，要留意。
5. 钥匙：由人提供，`export DEEPSEEK_API_KEY=YOUR_API_KEY`。没有就停，告诉用户「缺 DeepSeek API key，需你本人去 https://platform.deepseek.com 建」，不要自己代答。
6. 跑：`cd $W && dsh headless "<该期提示词>"`，提示词怎么取照该期 README「复现」里那行（第1、3期整份 `prompt.md`；第2期把占位 `[绝对路径或相对.]` 换成 `.`；第4期取 ``` 围栏内）。
   - 默认模型：`deepseek-flash`（DeepSeek-V4.1-Flash），reasoningEffort `high`。要换模型，写一个 patch 文件，内容是 `- id: agent-default-model` 加上 `config: {provider: deepseek-official, model: deepseek-v4-pro}`，然后跑 `dsh --profile headless --patch <该文件> "<任务>"`。`dsh --profile headless --dump-config` 可以看最终配置。
   - headless 不组合 agent preset：期目录 `dsh/*.patch.yml` 里的预设在 headless 下**不生效**，规矩靠第 3 步拷进去的 `AGENTS.md`。
   - 会话记录在 `$HOME/.dsh/sessions/` 下，可作 DSH 真跑过的证据。
   - 只跑一次 `dsh headless`。它不替 DSH 改产出，也不再追一轮 headless 让 DSH 修；验收不过就如实报哪条不过。
7. 验收：照该期 `README.md`「验收」逐条过，再和 `sample/` 比结构（目录、文件数），不比措辞；原件一律 `cmp`。第2期另核：文件总数 51 不变、逐个 `cmp`、无删除。

## 红线

- 没装上 DSH 或没钥匙时，**不许**自己手写/脚本生成产出冒充复现。要么停下报卡点，要么明说「这是它自己做的，不是 DSH 跑的」。
- 不 push、不开 PR、不写远端。
- 钥匙不进任何文件、不进日志。
- 不投递、不开招聘站（第 4 期）。

## 必须人做的

| 步骤 | 为什么 |
|---|---|
| 建 DeepSeek API key、给它 | 要登录、要付费 |
| DSH 桌面端 / `dsh web` 里点选 | GUI，它点不了；它走 `dsh headless` |
| 拿真简历/真账单/真纪要/真下载夹替换虚构样本 | 隐私 |
| 投递、付款等最后一步 | 红线 |
