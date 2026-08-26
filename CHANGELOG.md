# Changelog

## [0.0.2]

### Changed

- 重构：将 `User` 实体重命名为 `Learner`，更准确地反映学习者主体
- 为 `Learner` 实体添加 `user_id` 字段，预留关联 auth 领域的用户 ID
- 更新 `Completion` 实体的外键引用为 `learner_id`

## [0.0.1]

### Added

- 核心领域模型定义（User、Criterion、Completion）
- 实体关系说明
