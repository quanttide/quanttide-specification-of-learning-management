# 量潮学习管理标准

核心模型：**Learner** × **Completion**（标准实体层）＋ **Schedule** + **Task**（核心领域模型层）

本领域模型由 quanttide-learn-toolkit 承载（JSON 契约定义），分两层：

- **标准实体**：Learner × Completion，已由学习云 provider 实现（见 `learner/`）
- **核心领域模型**：Schedule + Task，设计完成未落码（见 `schedule/`）

## 实体

### Learner（学习者）

本领域的学习者主体。

```
Learner {
  id: uuid          # 本领域学习者 ID
  user_id: uuid     # 可选，预留，关联 auth 领域用户 ID
  schedule_id: uuid # 可选，→ Schedule.id，跟随的学习路径
}
```

### Completion（完成记录）

Learner 沿 Schedule 完成 Task 的通过记录，Task 的验收判定写在其自身描述中，此处只记状态。

```
Completion {
  id: uuid          # 主键
  learner_id: uuid  # → Learner.id
  task_id: uuid     # → Task.id
  status: enum      # completed | not_completed
  created_at: datetime # 创建时间
  updated_at: datetime # 更新时间
}
```

### Schedule（学习路径）

学习管理体系的核心领域模型——Task 的有序集合，探路者—跟随者结构的枢纽。

```
Schedule {
  id: uuid          # 唯一标识
  title: string     # 名称
  description: string # 可选，描述
  tasks: Task[]     # Task 有序数组，不引入额外层级实体
}
```

### Task（任务）

路径上的一个节点——「学什么、做什么、做到什么程度算过」的最小单位，自足、自描述。

```
Task {
  id: uuid          # 唯一标识
  title: string     # 标题
  description: string # 验收判定写进描述，不引用外部概念
}
```

## 关系

```
Learner ──1:N──▶ Completion ◀──N:1── Task（Task 属于 Schedule）
```

## 文档结构

- `learner/`：标准实体——`learner.md`（Learner）、`completion.md`（Completion）
- `schedule/`：核心领域模型——`schedule.md`（Schedule）、`task.md`（Task）
