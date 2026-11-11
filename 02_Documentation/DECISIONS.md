# Decision Log

V0.1。仅记录已确认的项目组织及架构决定；Proposal 目标不自动成为已实施或已验证决定。

## Confirmed Decisions

| Decision ID | Date | Topic | Decision | Rationale | Status |
| --- | --- | --- | --- | --- | --- |
| D001 | 2026-11-11 | Work management | 使用 12 Work Packages 管理任务 | 按用户 V0.1 初始化要求分解依赖及交付物 | Confirmed |
| D002 | 2026-11-11 | Artifact placement | 使用独立开发目录存放实际成果 | 分离任务管理与开发成果，避免重复维护 | Confirmed |
| D003 | 2026-11-11 | Codex context | 使用项目级 AGENTS.md 补充适用全局规则 | 保留仓库上下文、科研与操作边界 | Confirmed |
| D004 | 2026-11-11 | Implementation scope | 当前阶段不锁定技术实现方案 | 本次只做 repository skeleton/documentation | Confirmed |

## Entry Template

下表仅为未来经确认决定的填写模板，不构成决定。

| Decision ID | Date | Topic | Decision | Rationale | Status |
| --- | --- | --- | --- | --- | --- |
| Dxxx | YYYY-MM-DD | TBD | TBD | TBD | Proposed / Confirmed / Superseded |

## Open Topics (Not Decisions)

| Topic | Status | Detail |
| --- | --- | --- |
| Motor/drive selection, coupling and fixture design | Open | TBD |
| Software framework, communication and control modes | Open | TBD |
| Clocks, synchronization implementation and alignment tolerance | Open | TBD |
| Units, coordinate frames and calibration procedures | Open | TBD |
| Safety limits, stopping implementation and verification | Open | TBD |
| LeRobot version/schema and institutional/release approvals | Open | TBD |

重大决定确认后填写理由并更新相关接口与系统说明。琐碎实现细节不加入本表。
