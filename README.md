<!-- 状态: 已定稿 | 定稿日期: 2026-09-01 -->

# 多人协同工作台（Mock 版）

模拟 AI Native 多人协作机制的文件工作区。协作双方：A（PLUS 频道页产品，对活动整体效果负责）与 B（频道页产品·实习生，负责活动落地页设计）。协作载体是文件 + Git，不使用即时通讯与会议。

> 业务原型：京东 PLUS × 苹果折叠屏 Ultra 首销"早鸟票"活动（Q3 S 级项目），简化为 A/B 两个角色运行。

## 目录索引

| 路径 | 用途 |
|---|---|
| `commons/contract.md` | 协作契约（规则总纲，最高优先级） |
| `commons/consensus/` | 共识文件（项目背景、目标、职责边界、决策沉淀） |
| `members/A/` | A 的成员区：`inbox/`（收件箱）、`drafts/`（草稿）、`deliverables/`（生效产出）、`archive/`（归档）、`workspace.md`（分步进度） |
| `members/B/` | B 的成员区（与 A 完全同构） |
| `logs/collaboration-log.md` | 全局协作日志（追加式，禁止修改历史条目） |

## AI 冷启动指引

任何协作者（或其 AI）每次开工，按以下顺序建立上下文：

1. 本文件——了解全局结构
2. `commons/contract.md`——明确规则与禁区
3. `commons/consensus/` 下的共识文件——业务背景与目标
4. 自己成员区的 `workspace.md`——当前分步进度
5. 自己成员区的 `inbox/`——筛选 `status: pending` 的待处理投递

## 运行规则（详见契约）

- 开工第一步永远是 `git pull`，完工即 `git push`
- 每个任务新开一个 AI 会话处理（上下文来自文件，不依赖会话记忆）
- 投递/回执/异议一律通过对方 `inbox/` 的文件完成，不直接修改他人成员区文件
- AI 产出一律先进 `drafts/`，经人工审核后才能转入 `deliverables/` 生效
