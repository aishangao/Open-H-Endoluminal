# WP02 - Endoscope Steering Mechanism

V0.1

## Objective

规划四方向内窥镜与两路近端转向驱动的机械耦合及反馈边界。

## Scope

覆盖 up/down 与 left/right bending 近端耦合、零位和行程；不把近端角度解释为远端 tip pose。

## Key Requirements

保留两路电机 commands、encoder feedback 和状态；零位及限位须记录并经后续验证。

## Dependencies & Interfaces

与 WP03 对接近端装配支撑，与 WP04 对接转向指令，与 WP05 对接约束，与 WP07 对接零位标定。

## Expected Deliverables

机构需求、耦合设计与装配说明、零位和行程记录定义；后续硬件成果置于 03_Hardware。

## Open Questions

电机型号、传动、encoder 类型、角度单位和限位数值 TBD。

## Status

Planning

## References

[Proposal](../../open-h-endoluminal.pdf) | [WP Index](../README.md) | [Interfaces](../../02_Documentation/INTERFACES.md)
