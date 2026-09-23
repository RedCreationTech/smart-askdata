# 红创智能问数系统 (Smart AskData)

Enterprise Semantic Data Agent.

## 产品定位

红创智能问数系统不是传统 BI 报表系统, 而是在企业数据与业务人员之间增加一层可对话的数据智能能力。

核心能力:

- 自然语言问数
- 知识图谱驱动业务语义理解
- 向量知识库增强检索
- 多数据库实时查询
- SQL 安全编译与执行
- 自动分析与可追溯回答
- 企业知识持续学习

## 技术路线

### Frontend

- ClojureScript
- React
- Reagent
- re-frame
- shadow-cljs
- Ant Design React
- ECharts
- AntV G6
- Monaco Editor

### Backend Control Plane

- Clojure
- Ring
- Reitit
- Malli
- Integrant
- PostgreSQL

### AI/Data Plane

- Python
- FastAPI
- LangGraph
- SQLGlot
- DuckDB
- PyArrow

## 核心架构

```
用户问题
  |
  v
Semantic Agent
  |
  +-- Knowledge Graph
  |
  +-- Vector Knowledge Base
  |
  +-- Query Planner
  |
  v
SQL Compiler + Policy Guard
  |
  v
Database Connector
  |
  v
Enterprise Data Sources
```

## 开发原则

1. 模型负责理解, 程序负责执行。
2. 指标语义优先于 SQL 生成。
3. 所有答案必须可追溯。
4. 知识必须版本化管理。
5. 权限必须在查询执行前验证。

## 文档

- docs/architecture/system-design.md
- docs/architecture/adr.md
- docs/development/roadmap.md
