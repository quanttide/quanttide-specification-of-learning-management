# 量潮学习管理标准

核心模型：**Learner** × **Criterion** → **Completion**

## 实体

### Learner（学习者）

本领域的学习者主体。

```
Learner {
  id: uuid      # 本领域的学习者 ID
  user_id: uuid # 预留，关联 auth 领域的用户 ID
}
```

### Criterion（验收标准）

学习的原子单元，由课程档案定义。

```
Criterion {
  id: uuid              # 标准标识
  title: string         # 语义标识，如 "vibe-coding/lesson1/zed-connection"
  description: string   # 具体规则描述
}
```

### Completion（完成记录）

User 与 Criterion 的交叉记录，记录通过状态。

```
Completion {
  id: uuid              # 主键
  learner_id: uuid      # → Learner.id
  criterion_id: uuid    # → Criterion.id
  status: enum          # completed | not_completed
  created_at: datetime  # 创建时间
  updated_at: datetime  # 更新时间
}
```

## 关系

```
Learner ──1:N──▶ Completion ◀──N:1── Criterion
```
