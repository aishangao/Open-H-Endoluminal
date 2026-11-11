# WP04 - Teleoperation and Control

V0.1

## Objective

规划 Xbox 输入到近端转向和 UR5 外部夹具运动的操作语义。

## Scope

定义操作者 enable、转向及 insertion/retraction 映射边界；不实现自主导航。

## Key Requirements

分别保存 Operator Input 与 actuator/robot Command，不能用指令代替反馈；遵循 WP05 的使能和停止要求。

## Dependencies & Interfaces

输入来自 Xbox，输出到 WP02 steering drive 与 WP03 UR5；向 WP06 提供输入和指令记录，与 WP05 对接安全状态。

## Expected Deliverables

输入映射说明、控制职责与状态定义；后续实现置于 04_Software。

## Open Questions

按键映射、缩放、控制模式、软件框架、协议和更新周期 TBD。

## Status

Planning

## References

[Proposal](../../open-h-endoluminal.pdf) | [WP Index](../README.md) | [Interfaces](../../02_Documentation/INTERFACES.md)
