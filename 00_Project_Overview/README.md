# Project Overview

## Objective and Scope

以遥操作方式采集下消化道导航的同步 observation-action demonstrations，面向后续视觉语言动作学习与内腔感知研究。本阶段为 Planning，只建立文档和项目结构。

## Proposal Baseline

来源：[Proposal](../open-h-endoluminal.pdf)，§1–3。计划平台包括四方向内窥镜、两路近端转向电机及 encoder feedback、dual-arm UR5 外部插入/支撑夹具、Xbox 和 RGB video。原生转向驱动信号不可由支撑臂信号替代。远端 tip pose 不直接测量；外部夹具运动不等于真实腔内插入深度。

任务顺序为 lumen alignment、advancement through bends、designated-region observation、withdrawal。每种物理场景计划约 50% translation-dominant、50% articulation-requiring trajectories；记录 strategy label 与 configuration/specimen ID。这是采集策略目标，不是已达到的分布。

## Commitments and Milestones

- Phantom: 4 usable hours；ex-vivo porcine colon: 4 usable hours；合计 8 usable synchronized hours。
- Ex-vivo 4 小时满足 Proposal 所述 S1 最低要求；phantom 4 小时不独立满足该场景 8 小时最低要求。
- 初始同步样本：2026-12-01；最终交付：January 2027，具体日期 TBD。
- 计划交付 LeRobot dataset、frame-aligned action descriptions、基本标定及平台说明。

Proposal §3 Table 2 的采集目标：RGB 30 fps、Xbox 50 Hz、steering drive 至少 50 Hz、dual-arm UR5 至少 50 Hz。实际速率、丢样、间隙及对齐误差须由后续记录证明；验收容差 TBD。

## Governance and Open Questions

Proposal §3.4、§6 计划仅在 phantom 与 ex-vivo 场景采集，默认不录音；组织来源、处理与处置遵循机构程序，实验前取得适用批准。计划以 OpenMDW-1.1 发布获准数据并贡献至 HuggingFace；这不是当前发布授权，也不自动决定仓库代码许可。审批、来源安排、实际平台状态、责任人、实现选型和验收参数 TBD。

## Navigation

任务管理见 [Work Packages](../01_Work_Packages/README.md)，系统关系见 [Documentation](../02_Documentation/README.md)，来源定位见 [References](../08_References/README.md)。
