# Schedule（学习路径）

学习管理体系的核心领域模型——Task 的有序集合，探路者—跟随者结构的枢纽。属核心领域模型层（quanttide-learn-toolkit 承载，JSON 契约定义，设计完成未落码）。

## 字段

- `id`: 必选，唯一标识。
- `title`: 必选，名称。
- `description`: 可选，描述。
- `tasks`: 必选，Task 有序数组；顺序、依赖、分组经数组次序与 Task 间关系表达，不引入额外层级实体。

## JSON 示例

```json
{
  "id": "schedule-agent-engineer",
  "title": "智能体工程师训练营",
  "description": "按学习路径推进的训练计划，主线是建设数据工程第二大脑。",
  "tasks": [
    {
      "id": "task-data-second-brain",
      "title": "熟悉数据工程第二大脑",
      "description": "以新人视角通读领域第二大脑，记录困惑并提出改进建议。达成：至少一条建议经 Issue 讨论达成共识后进入 PR。"
    },
    {
      "id": "task-data-intention",
      "title": "整理数据工程意图",
      "description": "从数据工程日志考古组织意图，增加最新想法，描绘量潮为什么想要建设数据工程第二大脑。"
    }
  ]
}
```
