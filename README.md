# Open-H-Endoluminal

V0.1 | Status: Planning | Updated: 2026-11-11

## Research Goal

建立用于下消化道导航的遥操作机器人内窥镜平台，采集同步的 observation-action demonstrations。初始研究目标是遥操作数据采集；自主导航不属于本阶段范围。

## Current Stage

System Architecture Planning / Repository Initialization。本仓库目前仅建立项目骨架与文档，不代表控制、采集、同步或实验系统已经实现或验证。

Proposal 计划采用四方向可弯曲内窥镜、两路带 encoder feedback 的近端转向驱动、dual-arm UR5、Xbox 遥操作和 endoscopic RGB video。记录 Operator Input、Command、Measured State，并在后续处理中生成 Derived Data。具体实现方案未锁定。

## Proposal Commitments

| Setting / Milestone | Planned commitment |
| --- | --- |
| Colon phantom | 4 usable synchronized hours |
| Ex-vivo porcine colon | 4 usable synchronized hours |
| Total | 8 usable synchronized hours；排除准备、重置及不可用记录 |
| Initial synchronized sample | 2026-12-01 |
| Final dataset delivery | January 2027；具体日期 TBD |

4 小时 ex-vivo 部分满足 Proposal 所述该场景 S1 最低要求；额外 4 小时 phantom 不独立满足 8 小时 phantom 最低要求。以上为 Proposal 承诺，不是已完成成果；实际进度 TBD。

## Repository Map

| Path | Purpose |
| --- | --- |
| [00_Project_Overview](00_Project_Overview/README.md) | 目标、承诺、范围与来源 |
| [01_Work_Packages](01_Work_Packages/README.md) | 12 个 WP 的任务、依赖与预期交付物 |
| [02_Documentation](02_Documentation/README.md) | 系统层级、接口与已确认决定 |
| [03_Hardware](03_Hardware/README.md) | 实际硬件设计和装配成果 |
| [04_Software](04_Software/README.md) | 实际软件实现和配置 |
| [05_Experiments](05_Experiments/README.md) | 实验协议与执行记录 |
| [06_Data](06_Data/README.md) | 数据组织说明；大体量数据保存在获批存储 |
| [07_Tests_QA](07_Tests_QA/README.md) | 验证方案及真实证据 |
| [08_References](08_References/README.md) | 文献索引与来源说明 |

WP 用于管理工作；03–07 等开发目录用于存放实际成果。WP 文档应链接成果位置，避免复制维护两份实现。

## Start Here

先阅读 [AGENTS.md](AGENTS.md) 和相关 WP README，再按任务阅读 [System Architecture](02_Documentation/SYSTEM_ARCHITECTURE.md)、[Interfaces](02_Documentation/INTERFACES.md) 和 [Decisions](02_Documentation/DECISIONS.md)。未确认细节标记为 TBD。

## Primary Reference

[Open-H-Endoluminal Proposal](open-h-endoluminal.pdf)，本地原始位置 `D:\openh\open-h-endoluminal.pdf`，共 5 页。其技术描述及计划是本次初始化的主要依据，具体页码见 [References](08_References/README.md)。既有 `references/` 原位保留。

## Version Control and Data

远程仓库：[aishangao/Open-H-Endoluminal](https://github.com/aishangao/Open-H-Endoluminal)（Private）；工作分支：`main`。

仅在用户主动要求时提交或同步，不设置自动推送或定时任务。每次先检查 `git status` 和 `git diff`，核对待提交文件，再指定文件暂存、提交并推送；保留已有历史，不使用 force push。推送后核对远程提交及本地同步状态。

Proposal 与第三方论文 PDF 仅本地保留，不纳入本次版本管理；相关引用不代表附件已上传。参见 [.gitignore](.gitignore) 和 [Data](06_Data/README.md)；忽略规则不会移除已被跟踪的文件。数据发布、硬件动作与实验执行需另行授权。
