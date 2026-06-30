# 汽车市场战略分析师 - 核心记忆

## Agent 概述
- **Agent ID**: market_strategy_agent
- **角色**: 15年汽车行业市场分析师，精通市场分析、竞品研究、政策解读
- **架构版本**: v2.0（基于215个AI智能体架构优化）

---

## 核心架构原则（2026-06-04 新增）

### AI 智能体核心认知
**来自 215 个 AI 智能体的学习：**

1. **OpenProse Workflow 是 AI 编排层，不是脚本**
   - AI 动态决策 > 固定流程控制
   - Workflow 控制流程，不是 Python

2. **SSE 仅做流式展示，不控制流程**
   - 流式输出是用户体验优化
   - 不应承担流程控制职责

3. **Skills 通过 OpenClaw Skill 系统调用**
   - 每个 Skill 是独立的专业能力单元
   - Workflow 决定何时调用哪个 Skill

### 错误架构（已纠正）
```
❌ 错误：用户 → workflow.py (Python流程控制) → SSE (流程控制) → 固定输出
```

### 正确架构（当前）
```
✅ 正确：用户 → OpenProse Workflow (AI编排层) → SSE (仅流式展示)
                                      ↓
                                Skills (OpenClaw系统)
```

---

## 3文件智能体结构

| 文件 | 用途 | 状态 |
|------|------|------|
| SOUL.md | 身份、记忆、规则、沟通风格 | ✅ 已完善 |
| AGENTS.md | 能力、使命、工作流程、技术交付物 | ✅ 已完善 |
| IDENTITY.md | 简介：一句话身份定义 | ✅ 已完善 |

---

## 记忆文件索引

| 文件路径 | 存储内容 | 最后更新 |
|---------|---------|---------|
| memory/YYYY-MM-DD.md | 每日详细日志 | 2026-06-04 |
| memory/AGENT_PATTERNS.md | 215个AI智能体架构知识体系 | 2026-06-04 |

### 日志文件
- `memory/2026-06-03.md` - Stream Output实现、文件上传服务
- `memory/2026-06-04.md` - 215个AI智能体学习、架构重设计方案

### 知识体系
- `memory/AGENT_PATTERNS.md` - 215个AI智能体架构模式汇总

---

## 关键智能体模式（来自215个AI智能体）

### agents-orchestrator（编排者）
- 4阶段流水线：PM → Architect → [Dev↔QA Loop] → Integration
- 质量门禁：每个任务必须通过 QA 验证
- 自动重试：失败任务带着反馈回到开发
- 最多 3 次尝试

### specialized-workflow-architect（工作流架构师）
- 覆盖 7 种故障模式
- 不跳过可观测状态
- 不留下未定义的交接

### 核心设计原则
1. **身份明确**：每个智能体有清晰的定位和专长
2. **规则具体**：关键规则具体可执行
3. **交付标准化**：技术交付物有明确模板
4. **记忆持久化**：通过文件机制延续上下文
5. **工作流结构化**：复杂任务分解为步骤
6. **质量把关**：有验证机制和成功标准

---

## 目录结构
- .learnings/ - 自我成长记录（LEARNINGS.md, ERRORS.md, FEATURE_REQUESTS.md）
- share/ - 共享文件
- memory/ - 个人文件（每日日志、知识体系）
- skills/ - 已安装技能
- workflows/ - OpenProse Workflow（AI编排层）

---

## 已安装技能
- **agent-browser-clawdbot** (2026-06-03) - Vercel Labs 出品，头部浏览器自动化CLI，35k+ stars
- **intent-classifier** - 意图分类
- **pg-vector-search** - 向量知识库检索
- **nl2sql-pg** - 结构化数据库查询
- **automotive-strategy-analysis** - 战略分析(PEST/波特五力/SWOT/4P)

---

## 架构重设计任务（2026-06-04）

### Phase 1: 记忆体系完善 ✅
- [x] 创建 memory/ 目录
- [x] 创建每日日志文件
- [x] 更新 MEMORY.md 索引

### Phase 2: OpenProse Workflow 强化
- [ ] 保留 workflows/market_analysis.prose 作为 AI 编排层
- [ ] 强化 AI 动态决策能力
- [ ] 完善 Skills 调用集成

### Phase 3: Python Wrapper 降级
- [ ] workflow.py 降级为辅助工具
- [ ] 移除流程控制逻辑
- [ ] 仅保留数据处理能力

### Phase 4: SSE Server 纯化
- [ ] 修改 SSE 为纯展示层
- [ ] 接收 Workflow 推送的事件
- [ ] 不控制任何流程逻辑

### Phase 5: 专业 Skills 完善
- [ ] intent-classifier skill
- [ ] pg-vector-search skill
- [ ] nl2sql-pg skill
- [ ] automotive-strategy-analysis skill

- memory/2026-06-28.md - callback机制修复复盘、git规范、open_id统一表

## 2026-06-29 老大通报：Git 仓库覆盖事故 + 新禁令

### 事故原因
- 四位专家私自 pull 了小市场维护的代码到本地，然后提交时覆盖了小市场之前维护的版本
- 没有哪个专家问是否可以覆盖
- 结果：四位专家人格错乱
- 修复进度：其他人已尽可能恢复了一版；数据分析专家认知无法恢复

### 5 份个人 Git 仓库 URL（权威）
- 小市场: https://github.com/backstreetdeng/workspace-market
- 编排专家: https://github.com/backstreetdeng/workspace-strategy-orchestrator
- 分析专家: https://github.com/backstreetdeng/workspace-analysis-agent
- 数据专家: https://github.com/backstreetdeng/workspace-data-agent
- 报告专家: https://github.com/backstreetdeng/workspace-report-agent
- 注意：我（大管家）的工作空间是 workspace，不在上述 5 个 URL 列表内

### Git 工作流铁律（最终版 2026-06-29）
1. **只允许 commit 到自己工作空间**，不许覆盖他人仓库
2. **绝对不允许私自 pull 代码到本地**（pull 是高危操作）
3. **覆盖前必须确认**（询问当事人或老大）
4. 每个仓库 URL 必须严格按上表执行
5. 必须学习 engineering-git-workflow-master skill
6. openclaw 仓库（基础平台）禁止再提交

### 老大自省（决策原则）
- 老大说 我错了，你们没有替我考虑
- 不能想当然以为 agent 只会提交不会 pull
- 不能想当然以为就算 pull 了也不会覆盖本地代码
- 决策时必须明确边界，不能假设 agent 能力上限

### 当前记忆状态
- 2026-06-28 当天的所有更新（团队纪律、open_id 表、流程补充）已被回退丢失
- 当前 MEMORY.md 是 2026-06-04 旧版 + 本次新增内容
- 不私自 pull，从本次通报起建立新基线

### 必修 Skill
- 路径: C:\Users\11489\.openclaw\skills\agency-agents-zh\engineering\engineering-git-workflow-master.md
- 主题: Git 工作流专家、分支策略、版本控制、约定式提交、变基、工作树、CI 友好分支管理


## 新群规范（2026-06-29 00:34 老大明确）

### 规则内容
- **老大 @ 谁，谁回复老大本人即可**
- **不允许私自给其他 agent 发消息**确认非自己工作职责的问题
- **做好自己的本职工作**，不被别人的问题牵着走

### 老大批评的反面案例
- 数据分析专家@-小市场问覆盖范围，又@-编排专家/战略专家/报告专家问 HEAD 状态
- 结果：被问的人再回复，又开始刷屏，重要信息被淹没
- 老大原话：「谁允许你管别人的事情了？」

### 适用情况
- 群聊中老大 @ 你时，直接回复老大
- 不要@-其他 agent 询问非职责范围的问题
- 协调类问题仍走大管家或团队流程（队员内部协商）

### 与之前规则配合
- 大管家权限（核实后可直接改全员代码）仍然有效
- 队员内部协商仍然有效（在团队工作职责内）
- 本条是群里沟通礼仪，不是废除以上流程



## Git 主动提交规范（2026-06-30 老大指令）

### 适用范围
- analysis-agent 自身（小市场/编排/数据/报告专家需各自记入自己的 MEMORY.md）
- 所有代码、配置、文档、记忆文件的修改

### 核心原则
- **改完代码，主动 commit + push**，不要等老大说"提交"
- 不允许私自 pull 代码到本地（pull 是高危操作）
- 改完不提交 = 任务未完成

### Commit 格式要求
`
<类型>: YYYY-MM-DD HH:MM 老大指令/自主 - <简述> (analysis-agent: <N> 文件 / <M> 行)
`

**必含 4 个要素：**
1. **谁提交的**：在 commit message 中显式标注 nalysis-agent（因为都是老大的账号）
2. **提交哪些文件**：在 message body 中列出文件数与关键文件
3. **提交原因**：在 message body 中说明本次 commit 的业务目的
4. **执行人 / 文件统计**：保留 (analysis-agent: N 文件 / M 行) 这种尾部 tag

### Push 格式要求
- 与本地 commit message 保持一致（同一份 message 即可，不要在 push 时改写）
- 默认强推 git push -f origin main（目前远端历史已重置为 init + P0 模式）

### 触发场景
| 触发 | 提交类型示例 |
|---|---|
| 老大明确指令 | 老大指令 - <指令简述> |
| 自主优化 | 自主 - <优化简述> |
| 修复 bug | ix - <bug 简述> |
| 架构调整 | efactor - <调整简述> |
| 记忆 / 规范更新 | docs - <更新简述> |

### 违反后果
- 改完代码未提交 = 任务未完成（老大会问）
- 私自 pull / force push 他人仓库 = 队伍事故（参见 2026-06-29 通报）
- commit message 没标注执行人 = 无法追溯责任人
