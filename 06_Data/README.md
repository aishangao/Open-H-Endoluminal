# Data

V0.1 | Status: Planning

## Purpose and Boundaries

本目录说明数据组织、存储引用和字段文档。原始数据、处理结果、导出数据必须分开；大体量或敏感实验材料保存在机构获批存储中，不能默认进入 Git。本次不生成数据或创建流水线。

## Planned Layout

以下仅为后续命名约定，目录尚未创建，格式与存储映射 TBD：

| Path | Intended content |
| --- | --- |
| raw/ | 原始 video、input、commands、measured states 与 session metadata；保留原始时间戳 |
| processed/ | 对齐、标注与派生数据，保留 source IDs 和转换 provenance |
| exported/ | 经 QA 与权限审查的 LeRobot export |
| local/ | 本地受限存储索引或配置，不进入 Git |

这些路径在根 [.gitignore](../.gitignore) 中忽略。不要在其他路径提交 recordings 或敏感元数据；Git ignore 不是权限控制，也不会移除已跟踪文件。明确批准的小型非敏感测试 fixtures 可放 `07_Tests_QA/fixtures/`，加入 Git 前人工审查内容和体量；不要宽泛解除数据忽略规则。

## Metadata and Semantics

保留 units、coordinate frames、clock identity、timestamps、task intent/target、platform、setting、modality、synchronization method/error、actual rates、licence/de-identification status、operator study code/experience、specimen/configuration ID 和 strategy。Command 与 Measured State 分开，Derived Data 标明来源。元数据 schema、访问权限和存储路径 TBD。

## Work Package Relationship

WP06 负责采集，WP07 负责同步与标定，WP09 负责处理标注，WP10 提供 QA，WP11 负责打包与治理。具体任务见 [WP Index](../01_Work_Packages/README.md)。任何发布或上传需明确授权和适用审查。
