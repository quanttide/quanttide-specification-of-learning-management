# 核心领域模型

qtcloud-learn 的核心模型：**User** × **Criterion** → **Completion**

## 实体

### User（用户）

学员，ID 来自 auth 领域，本领域只引用。

```
User {
  id: uuid    # 引用 auth 领域的用户 ID
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
  user_id: uuid         # → User.id
  criterion_id: uuid    # → Criterion.id
  status: enum          # completed | not_completed
  created_at: datetime  # 创建时间
  updated_at: datetime  # 更新时间
}
```

## 关系

```
User ──1:N──▶ Completion ◀──N:1── Criterion
```
