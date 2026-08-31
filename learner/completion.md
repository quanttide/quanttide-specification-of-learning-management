# Completion（完成记录）

Learner 沿 Schedule 完成 Task 的通过记录，Task 的验收判定写在其自身描述中，此处只记状态。属标准实体层（quanttide-learn-toolkit 承载，JSON 契约定义，已由学习云 provider 实现）。

## 字段

- `id`: 必选，主键（uuid）。
- `learner_id`: 必选，→ Learner.id。
- `task_id`: 必选，→ Task.id。
- `status`: 必选，`completed` / `not_completed`，二元枚举。
- `created_at`: 可选，创建时间。
- `updated_at`: 可选，更新时间。

## JSON 示例

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
