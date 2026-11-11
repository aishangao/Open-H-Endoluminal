# System Architecture

V0.1 | Status: Planning

## Basis and Boundary

依据 [Proposal](../open-h-endoluminal.pdf) §3；下表描述计划职责，不表示已部署或验证，也不批准具体软件架构。当前仅做遥操作同步数据采集的系统规划。

| Layer | Responsibility and Basic Relationships | Related WP |
| --- | --- | --- |
| Physical Hardware | 四方向内窥镜、两路近端转向驱动/encoders、dual UR5 和外部夹具；接受控制并提供可采集原生状态 | WP02, WP03 |
| Teleoperation Interface | Xbox axes/buttons、enable 和事件输入；向控制层提供 Operator Input | WP04, WP05 |
| Robot and Actuator Control | 解释操作语义并生成 steering/UR5 Command；受 enable、停止和运动约束控制 | WP04, WP05 |
| Sensor and State Acquisition | 记录 RGB、Operator Input、Command、Measured State、原始时间戳及流状态 | WP06 |
| Synchronization and Calibration | 为采集流建立时间关系，记录 motor zero/limits 和 robot tool/insertion references，保留误差与转换来源 | WP07 |
| Experimental Environment | 配置 phantom 和 ex-vivo 场景，提供 configuration/specimen IDs 与准备记录；执行适用机构程序 | WP01, WP08 |
| Data Processing and Annotation | 基于原始流与对齐结果组织 episodes、时间区间和 frame-aligned labels，产生可追溯 Derived Data | WP09 |
| Dataset Packaging and Quality Assurance | 完整性、对齐、标注与可用时长审查；组织 LeRobot 交付及权利、隐私和发布审查 | WP10, WP11 |

WP12 协调层间依赖。硬件与实验环境提供物理条件；操作输入经控制产生动作；采集记录输入、指令和反馈；同步、处理、QA 与治理形成后续交付链。QA 反馈可要求重新采集或剔除片段，不能回填虚构测量。

## Semantics and Limits

- Operator Input 是 Xbox 操作；Command 是发给执行器或机器人的目标；Measured State 是设备反馈；Derived Data 是对齐、转换或标注产生的结果。
- Encoder angles 描述 proximal steering drive，不是直接测得的 distal endoscope pose。
- UR5 tool poses 描述 external fixture，不是已验证的 intraluminal insertion depth；若姿态由关节状态计算，应标明其派生来源。
- Proposal 计划尽可能共享采集时钟，并在需要时检查和校正独立时钟偏移；具体同步实现与误差容差 TBD。
- Software framework、进程部署、通信协议、控制模式、设备型号、数值限位和精确 frames TBD。

接口见 [INTERFACES.md](INTERFACES.md)，已确认决定见 [DECISIONS.md](DECISIONS.md)。
