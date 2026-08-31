# Learner（学习者）

学习管理领域的学习者主体，属标准实体层（quanttide-learn-toolkit 承载，JSON 契约定义，已由学习云 provider 实现）。

## 字段

- `id`: 必选，本领域学习者 ID（uuid）。
- `user_id`: 可选，预留，关联 auth 领域用户 ID。
- `schedule_id`: 可选，→ Schedule.id，学习者跟随的学习路径（自助学习者无 Schedule，不填）。

## JSON 示例

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "user_id": "6f9619ff-8b86-d011-b42d-00cf4fc964ff",
  "schedule_id": "schedule-agent-engineer"
}
```
