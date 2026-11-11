# WP09 - Data Processing and Annotation

V0.1

## Objective

规划同步 episode 的 action descriptions、任务文本和 strategy labels。

## Scope

覆盖 steering、advancement、inspection、withdrawal 的区间标注和 frame mapping；保留原始数据与转换来源。

## Key Requirements

区分 Operator Input、Command、Measured State 和 Derived Data；每个 episode 有任务说明与 strategy/configuration 标识，标注不可冒充传感器测量。

## Dependencies & Interfaces

接收 WP01 任务定义、WP07 对齐数据和 WP08 场景信息；向 WP10 提交标注质量检查对象，向 WP11 提供可打包字段。

## Expected Deliverables

标注指南、标签与区间 schema 草案、后续处理和标注成果；代码放 04_Software，数据布局见 06_Data。

## Open Questions

标签边界规则、重叠动作处理、schema、复核流程与一致性标准 TBD。

## Status

Planning

## References

[Proposal](../../open-h-endoluminal.pdf) | [WP Index](../README.md) | [Interfaces](../../02_Documentation/INTERFACES.md)
