# Interfaces

V0.1 | Status: Planning

## Data Semantics

- **Operator Input**：操作者 axes/buttons、enable state、event markers。
- **Command**：发送至 steering drive 或 UR5 的目标指令，不作为实际运动证据。
- **Measured State**：encoder、UR5 measured joint states 及设备反馈状态。直接反馈与由反馈计算的字段须分别标明来源。
- **Derived Data**：对齐索引、时间校正结果、坐标变换、计算姿态、标签及导出字段；保留原始信号和转换来源。

## Initial Interface Register

所有行目前均为 Planning。传输协议、序列化格式、schema 和具体参数均 TBD；表中采样率只引用 Proposal §3 Table 2 的采集目标，不是已实现接口保证。最终字段的单位、时钟和 frame 定义须在实现前确认。

| Interface | Source | Destination | Information Exchanged | Units / Frames | Status / Open Questions |
| --- | --- | --- | --- | --- | --- |
| Xbox → Control | Xbox teleoperation | Control | Operator Input: axes/buttons, enable, event markers | Axis ranges、button semantics、timebase TBD；无空间 frame 默认假设 | Planning；mapping、protocol、format TBD；采集目标 50 Hz |
| Control → Steering Motors | Control | Two proximal steering channels | Command: bounded steering targets, enable/stop intent | Command mode、units、signs、zero、limits TBD | Planning；drive API、protocol、format、参数 TBD |
| Control → UR5 | Control | Dual-arm UR5 | Command: external fixture advancement/retraction and support motion | Joint/task units、base/tool frames、mode TBD | Planning；coordination、protocol、format、参数 TBD |
| Steering Motors → Data Acquisition | Steering drive / encoders | Data Acquisition | Command record + Measured State: encoder positions, drive status, timestamps；两类分字段保存 | Encoder units、channel IDs、zero、timebase TBD | Planning；protocol、format TBD；采集目标至少 50 Hz |
| UR5 → Data Acquisition | Both UR5 controllers | Data Acquisition | Command record + Measured State: joint states, controller status；tool poses 须注明 controller report 或 Derived Data 来源 | Joint units、base/tool frames、pose convention、timebase TBD | Planning；protocol、format TBD；采集目标至少 50 Hz；外部夹具状态不是腔内深度 |
| Endoscope Camera → Data Acquisition | Endoscopic RGB camera | Data Acquisition | RGB frames, timestamps, capture settings, calibration references | Pixel layout、resolution、timebase、optical frame TBD | Planning；protocol、format TBD；采集目标 30 fps |
| Data Acquisition → Synchronization | Recorded streams | Synchronization | 原始 Operator Input、Command、Measured State、RGB、timestamps 与 gaps/drop records | 保留各流原始单位、frames 与 clock identity；定义 TBD | Planning；storage schema、clock implementation、format TBD |
| Synchronization → Dataset Processing | Synchronization / Calibration | Dataset Processing | 原始流引用及 Derived Data: alignment mappings、offsets、error estimates、calibration references | Time units、aligned timebase、frame transforms TBD；保留原始时间戳 | Planning；algorithm、interpolation policy、format、容差 TBD |
| Dataset Processing → LeRobot Export | Processing / Annotation | LeRobot Export | episodes、分离的 actions/states、frame-aligned labels、task text、metadata、QA 与 provenance | 字段映射、单位、frames、schema/version TBD | Planning；LeRobot version、format mapping、export 参数及验收 TBD |

## Related Boundaries

Xbox input 也必须被记录，Control 的 motor/UR5 commands 必须能够与设备反馈分别追溯；具体采集路径 TBD。Safety enable/stop、experimental metadata 和 calibration 需要关联至上述流，具体接口待各相关 WP 确认。本表不宣称完整的安全链路设计已获批准。

接口变化须由相关 WP 协调并更新本表；系统职责见 [SYSTEM_ARCHITECTURE.md](SYSTEM_ARCHITECTURE.md)。
