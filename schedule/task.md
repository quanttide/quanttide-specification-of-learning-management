# Task（任务）

路径上的一个节点——「学什么、做什么、做到什么程度算过」的最小单位，自足、自描述。属核心领域模型层（quanttide-learn-toolkit 承载，JSON 契约定义，设计完成未落码）。

## 字段

- `id`: 必选，唯一标识。
- `title`: 必选，标题。
- `description`: 必选，验收判定写进描述（做到什么程度算过），不引用外部概念。

## JSON 示例

```json
{
  "id": "task-data-second-brain",
  "title": "熟悉数据工程第二大脑",
  "description": "以新人视角通读量潮数据工程领域第二大脑（quanttide-data 主仓库、资产图式章程、发布管理章程），记录「知识诅咒」视角下的困惑，并提出改进建议。达成：至少一条建议经 Issue 讨论达成共识后进入 PR。"
}
```
