# 量潮学习管理标准

核心模型：**Learner** × **Criterion（课程域标准）** → **Completion**

本领域不设验收标准实体——Criterion 由课程云一等实体承载，学习云仅保存跨域引用并负责记录与聚合。

## 实体

### Learner（学习者）

本领域的学习者主体。

```
Learner {
  id: uuid      # 本领域的学习者 ID
  user_id: uuid # 预留，关联 auth 领域的用户 ID
}
```

### Completion（完成记录）

Learner 与课程域验收标准的交叉记录，记录通过状态。

```
Completion {
  id: uuid              # 主键
  learner_id: uuid      # → Learner.id
  criterion_id: uuid    # → 课程域 Criterion.id（同源直连）
  status: enum          # completed | not_completed
  created_at: datetime  # 创建时间
  updated_at: datetime  # 更新时间
}
```

## 关系

```
Learner ──1:N──▶ Completion ◀──N:1── Criterion（课程域）
```
