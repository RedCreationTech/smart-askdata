# 红创智能问数系统总体设计

## 1. 系统目标

构建企业级 Semantic Data Agent, 将企业数据库, 业务知识和人工经验连接起来。

系统通过:

- Knowledge Graph
- Vector Retrieval
- Database Query Engine

形成从业务问题到可信答案的完整链路。

## 2. 总体架构

```
React/ClojureScript Client
          |
          v
Clojure Core API
          |
          +----------------+
          | Semantic Layer |
          +----------------+
                  |
          +-------+--------+
          |                |
          v                v
 Knowledge Graph     Vector Knowledge
          |                |
          +-------+--------+
                  |
                  v
          Query Planning Agent
                  |
                  v
          SQL Compiler
                  |
                  v
          Policy Guard
                  |
                  v
        Database Connector Layer
                  |
                  v
 ERP MES LIMS CRM OA Database
```

## 3. 前端设计

前端采用 ClojureScript + React。

目录规划:

```
apps/web
  src/
    app/
    events/
    subscriptions/
    views/
    components/
    api/
```

状态模型采用 re-frame:

```
User Event
 -> Event Handler
 -> app-db
 -> Subscription
 -> React Component
```

## 4. 查询执行链

```
用户问题
 ↓
意图识别
 ↓
业务实体识别
 ↓
指标解析
 ↓
知识图谱召回
 ↓
向量知识检索
 ↓
QueryPlan
 ↓
SQL生成
 ↓
安全检查
 ↓
数据库执行
 ↓
结果校验
 ↓
答案生成
```

## 5. 数据层设计

PostgreSQL:

- 用户
- 权限
- 指标模型
- 图谱节点
- 知识版本
- 审计日志

DuckDB:

- 本地分析
- 临时数据集
- 向量检索加速
- 跨库归并

## 6. 技术原则

- 不直接 Text2SQL。
- 使用 QueryPlan 中间层。
- SQL 必须经过 AST 检查。
- 数据权限不能由模型决定。
- 知识发布必须可回滚。
