# Architecture Decision Records

## ADR-001 使用 ClojureScript + React

原因:

- 与红创技术体系统一
- 前后端共享 Clojure 数据模型
- 利于复杂企业应用长期维护

## ADR-002 使用语义层而不是直接 Text2SQL

原因:

- 企业指标需要统一口径
- 降低幻觉
- 支持版本管理

## ADR-003 QueryPlan 作为核心协议

原因:

- 分离理解和执行
- 支持安全审计
- 支持多数据库

## ADR-004 PostgreSQL 作为知识元数据中心

保存:

- 指标
- 图谱
- 权限
- 知识版本

## ADR-005 DuckDB作为本地计算加速层

用途:

- 分析计算
- 中间结果
- 本地检索

不是唯一生产知识存储。
