# WP07 - Synchronization and Calibration

V0.1

## Objective

规划 video-action-state 对齐及解释近端驱动和机器人信号所需的基本标定。

## Scope

覆盖 clock references、offset、motor zero/limits 和 tool/insertion references；不推定直接测得 distal tip pose。

## Key Requirements

Proposal 计划在可行时使用共同采集时钟，分离时钟时检查并校正偏移；保留时间戳，采集前短录制检查对齐，报告方法与观测误差。具体实现未批准。

## Dependencies & Interfaces

接收 WP06 原始流及 WP02/WP03 标定信息；向 WP09 提供对齐结果，向 WP10 提供误差证据，向 WP11 提供标定描述。

## Expected Deliverables

同步与标定规范草案、后续真实校准记录和对齐报告；设计归 02_Documentation，实现归 04_Software。

## Open Questions

时钟实现、offset 估计、重采样/插值方法、对齐容差与单位/frames TBD。

## Status

Planning

## References

[Proposal](../../open-h-endoluminal.pdf) | [WP Index](../README.md) | [Interfaces](../../02_Documentation/INTERFACES.md)
