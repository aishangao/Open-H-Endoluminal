# WP06 - Data Acquisition

V0.1

## Objective

规划 RGB video、Xbox、steering drive 与 dual-arm UR5 原生信号的完整记录。

## Scope

负责采集字段、时间戳、流状态和记录完整性；时间对齐归 WP07，标注和打包归 WP09/WP11。

## Key Requirements

Proposal 采集目标为 RGB 30 fps、Xbox 50 Hz、steering drive 和 dual-arm UR5 各至少 50 Hz；记录实际速率、间隙与丢样。commands 与 measured states 分开。

## Dependencies & Interfaces

输入来自 WP02–04 和相机；将带原始时间戳的流交给 WP07，向 WP10 提供采集健康与完整性信息。

## Expected Deliverables

流清单、字段与时间戳说明、记录流程设计；后续采集实现放 04_Software，数据组织见 06_Data。

## Open Questions

设备 API、协议、存储格式、时钟来源、缓冲和丢样处理 TBD。

## Status

Planning

## References

[Proposal](../../open-h-endoluminal.pdf) | [WP Index](../README.md) | [Interfaces](../../02_Documentation/INTERFACES.md)
