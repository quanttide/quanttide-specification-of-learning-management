# 学习者领域模型

quanttide-learn-toolkit 承载的学习管理领域模型，JSON 契约定义。本文件夹覆盖**标准实体层**：Learner × Completion（已由学习云 provider 实现）。

## Learner（学习者）

学习管理领域的学习者主体。

### 字段

- `id`: 必选，本领域学习者 ID（uuid）。
- `user_id`: 可选，预留，关联 auth 领域用户 ID。
- `schedule_id`: 可选，→ Schedule.id，学习者跟随的学习路径（自助学习者无 Schedule，不填）。

### JSON 示例

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "user_id": "6f9619ff-8b86-d011-b42d-00cf4fc964ff",
  "schedule_id": "schedule-agent-engineer"
}
```

## Completion（完成记录）

Learner 沿 Schedule 完成 Task 的通过记录，Task 的验收判定写在其自身描述中，此处只记状态。

### 字段

- `id`: 必选，主键（uuid）。
- `learner_id`: 必选，→ Learner.id。
- `task_id`: 必选，→ Task.id。
- `status`: 必选，`completed` / `not_completed`，二元枚举。
- `created_at`: 可选，创建时间。
- `updated_at`: 可选，更新时间。

### JSON 示例

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440001",
  "learner_id": "550e8400-e29b-41d4-a716-446655440000",
  "task_id": "task-data-second-brain",
  "status": "completed",
  "created_at": "2026-01-01T00:00:00Z",
  "updated_at": "2026-01-01T00:00:00Z"
}
```
