# AI Development Harness Template — 创建执行计划

> 文档用途：交给能力较弱的 Coding Agent 执行。
>
> **本 Agent 的任务不是设计 Harness，而是严格按照本计划创建目录和文档。**
>
> **核心原则：宁可少做、停下来报告，也不能自行发挥。**

---

# 1. 任务目标

创建一个可复制的、与具体项目无关的 AI Development Harness 模板。

模板用于以后创建：

- 微信小程序
- 游戏
- Web 应用
- 桌面应用
- 移动应用
- 后端服务
- AI 工具
- 其他软件项目

模板必须把：

```text
Human Product Owner
        ↓
Product
        ↓
Spec
        ↓
Design
        ↓
Task
        ↓
Implementation
        ↓
Test
        ↓
Verification
        ↓
Project State
```

固定成可执行的工程流程。

本次工作只创建 **Harness 模板本身**。

不得创建任何具体产品代码。

---

# 2. Agent 权限边界

## 2.1 Agent 可以做

Agent 可以：

1. 创建目录。
2. 创建 Markdown 文档。
3. 写入本计划明确要求的模板内容。
4. 创建必要的占位文件。
5. 检查目录结构。
6. 检查 Markdown 文件是否存在。
7. 修复自己创建过程中产生的明显格式错误。
8. 最后生成创建结果报告。

## 2.2 Agent 不可以做

禁止：

- 自行增加目录体系。
- 自行删除本计划要求的目录。
- 自行改变文件名称。
- 自行改变核心工作流。
- 自行增加产品功能。
- 自行加入某个具体项目的技术方案。
- 自行加入微信小程序、游戏、React、Vue、Node.js 等具体技术栈。
- 自行设计数据库。
- 自行实现 Coding Agent。
- 自行实现自动化脚本。
- 自行加入 CI/CD。
- 自行加入 MCP。
- 自行加入 GitHub 工作流。
- 自行添加“觉得有用”的规则。
- 把 TODO 当成已经完成。
- 在不确定时猜测。

### 最重要的规则

如果发现本计划存在：

- 冲突
- 缺失
- 歧义
- 无法判断
- 可能需要架构决策

**不要自行决定。**

必须停止当前步骤，并在最终报告中列出：

```text
问题：
影响：
需要 Human 决策：
建议选项：
```

---

# 3. 执行模式

严格按照以下阶段执行：

```text
Phase 0
读取本计划

↓

Phase 1
建立目录

↓

Phase 2
建立核心治理文件

↓

Phase 3
建立 Product 层模板

↓

Phase 4
建立 Spec 层模板

↓

Phase 5
建立 Design 层模板

↓

Phase 6
建立 Decision / Change / Task 层模板

↓

Phase 7
建立 Test / Verification / State 层模板

↓

Phase 8
建立 AI Governance 层模板

↓

Phase 9
建立 Future 层模板

↓

Phase 10
建立 README

↓

Phase 11
检查

↓

Phase 12
报告
```

不得跳过阶段。

---

# 4. 最终目录

必须创建以下结构：

```text
AI-Development-Harness/
│
├── PROJECT_CONTRACT.md
├── README.md
│
├── 00_PRODUCT/
│   ├── VISION.md
│   ├── PRD.md
│   ├── ROADMAP.md
│   └── NON_GOALS.md
│
├── 01_SPEC/
│   ├── CORE.md
│   ├── DOMAIN.md
│   ├── DATA.md
│   ├── BEHAVIOR.md
│   ├── UI.md
│   ├── API.md
│   ├── STORAGE.md
│   └── SECURITY.md
│
├── 02_DESIGN/
│   ├── ARCHITECTURE.md
│   ├── DATA_MODEL.md
│   ├── API_DESIGN.md
│   ├── UI_DESIGN.md
│   └── TECH_DECISIONS.md
│
├── 03_DECISIONS/
│   └── DECISIONS.md
│
├── 04_CHANGES/
│   ├── CHANGELOG.md
│   └── pending/
│
├── 05_TASKS/
│   ├── BACKLOG.md
│   ├── active/
│   └── completed/
│
├── 06_TESTS/
│   ├── TEST_STRATEGY.md
│   ├── unit/
│   ├── integration/
│   ├── acceptance/
│   └── regression/
│
├── 07_VERIFICATION/
│   ├── VERIFICATION_RULES.md
│   ├── reports/
│   └── failures/
│
├── 08_STATE/
│   ├── PROJECT_STATE.md
│   ├── IMPLEMENTATION_STATE.md
│   └── KNOWN_ISSUES.md
│
├── 09_AI/
│   ├── AI_RULES.md
│   ├── WORKFLOW.md
│   ├── SPEC_RULES.md
│   ├── TASK_RULES.md
│   ├── CHANGE_RULES.md
│   └── VERIFICATION_RULES.md
│
└── 99_FUTURE/
    └── IDEAS.md
```

---

# 5. 文件分类原则

必须理解以下层级。

## 5.1 Product

回答：

> 人类到底想做什么？

包含：

- Vision
- PRD
- Roadmap
- Non-goals

## 5.2 Spec

回答：

> 产品必须具有什么行为和规则？

Spec 是产品行为契约。

## 5.3 Design

回答：

> 用什么工程结构实现 Spec？

Design 不得反过来决定产品需求。

## 5.4 Task

回答：

> 下一步 AI 具体做什么？

## 5.5 Code

真正的软件实现。

本模板不包含具体 Code。

## 5.6 Test

回答：

> 怎么证明实现正确？

## 5.7 Verification

回答：

> 怎么证明 Task 完成且没有产品漂移？

## 5.8 State

回答：

> 项目现在到底是什么状态？

## 5.9 AI

回答：

> AI 应该如何工作，以及 AI 的权限边界是什么？

## 5.10 Future

回答：

> 以后可能想做什么？

Future 永远不是当前任务。

---

# 6. PROJECT_CONTRACT.md

必须创建，并作为最高优先级项目契约。

内容必须包含以下原则：

```markdown
# Project Contract

## Human Authority

Human owns:

- Product direction
- Product scope
- Feature decisions
- UX decisions
- Final acceptance
- Product priorities

## AI Authority

AI owns:

- Implementation
- Testing
- Debugging
- Refactoring
- Technical documentation
- Technical investigation
- Engineering execution

## AI MUST NOT

- Add unrequested product features
- Remove requested product features
- Change product direction
- Change locked product behavior
- Make unresolved product decisions
- Treat ideas as approved requirements
- Expand scope without approval
- Replace the product with a technically preferred alternative

## Uncertainty Protocol

When uncertain:

1. Identify the ambiguity.
2. Identify the affected requirement.
3. Explain the conflict.
4. Propose options if useful.
5. Stop before making a product decision.
6. Ask Human for the decision.

## Change Protocol

Any change to Product, Spec, locked Design, or scope must go through the change process.

## Definition of Done

A task is complete only when:

- Implementation is complete.
- Required tests pass.
- Acceptance criteria pass.
- No scope violation exists.
- No product drift exists.
- Project state is updated.
- Relevant documentation is updated.

## Source of Truth

When documents conflict, do not guess.
Report the conflict and request Human resolution.
```

Agent 不得扩写成自己的治理体系。

---

# 7. README.md

README 只负责说明：

1. 这个模板是什么。
2. 适合什么项目。
3. 如何复制。
4. 目录各自负责什么。
5. AI 的基本工作流程。
6. 如何开始一个新项目。

必须明确：

```text
This repository is a template.
It contains no product implementation.
```

不要加入具体产品案例。

---

# 8. 00_PRODUCT 文件

## VISION.md

模板必须包含：

```markdown
# Product Vision

## Product

[What is the product?]

## Problem

[What problem does it solve?]

## Target Users

[Who is it for?]

## Core Value

[Why should it exist?]

## Core Experience

[What should the user fundamentally be able to do?]

## Platform

[Target platform]

## Product Principles

[Core product principles]
```

---

## PRD.md

模板必须包含：

```markdown
# Product Requirements

## Goals

## Users

## Features

## User Flows

## Functional Requirements

## Non-Functional Requirements

## Acceptance Criteria

## Open Questions
```

必须提醒：

> PRD 是 Human-owned。

---

## ROADMAP.md

包含：

```markdown
# Roadmap

## Current Phase

## Completed

## In Progress

## Next

## Future

## Deferred
```

---

## NON_GOALS.md

包含：

```markdown
# Non Goals

## Explicitly Out of Scope

## Deferred Features

## Product Boundaries

## Anti-Drift Rules
```

必须明确：

> AI 不得因为“这些功能看起来合理”而实现它们。

---

# 9. 01_SPEC 文件

所有 Spec 文档必须遵循：

```text
Requirement
↓
Rule
↓
Expected Behavior
↓
Acceptance Condition
```

不能写成随意的产品介绍。

---

## CORE.md

包含：

```markdown
# Core Specification

## Core Concepts

## Core Rules

## Core User Flows

## Invariants

## Constraints

## Error Conditions

## Acceptance Rules
```

---

## DOMAIN.md

包含：

```markdown
# Domain Specification

## Domain Objects

## Relationships

## Ownership

## Lifecycle

## Invariants
```

---

## DATA.md

包含：

```markdown
# Data Specification

## Entities

## Fields

## Required Fields

## Optional Fields

## Validation

## Ownership

## Persistence Rules

## Data Lifecycle
```

不要设计具体数据库技术。

---

## BEHAVIOR.md

包含：

```markdown
# Behavior Specification

## User Actions

## Expected Responses

## State Transitions

## Loading

## Empty States

## Error States

## Edge Cases
```

---

## UI.md

包含：

```markdown
# UI Specification

## Screens

## Navigation

## Interaction Rules

## States

## Accessibility Requirements

## Responsive Requirements

## UI Constraints
```

不要指定具体 UI 框架。

---

## API.md

包含：

```markdown
# API Specification

## Operations

## Inputs

## Outputs

## Errors

## Authentication

## Authorization

## Idempotency

## Compatibility
```

这里只定义行为契约。

---

## STORAGE.md

包含：

```markdown
# Storage Specification

## Persistent Data

## Files

## Ownership

## Lifecycle

## Retention

## Deletion

## Backup Requirements
```

---

## SECURITY.md

包含：

```markdown
# Security Specification

## Authentication

## Authorization

## Data Isolation

## Sensitive Data

## Input Validation

## File Security

## Abuse Prevention

## Privacy Requirements
```

这里只定义要求，不选择具体安全产品。

---

# 10. 02_DESIGN 文件

Design 是技术实现层。

---

## ARCHITECTURE.md

包含：

```markdown
# Architecture

## System Overview

## Components

## Responsibilities

## Dependencies

## Data Flow

## Control Flow

## Boundaries

## Failure Handling

## Scalability Considerations

## Constraints
```

必须明确：

> Architecture 必须满足 Spec，不能为了技术方便修改 Spec。

---

## DATA_MODEL.md

包含：

```markdown
# Data Model

## Entities

## Relationships

## Keys

## Indexes

## Validation

## Migration Strategy

## Ownership

## Consistency
```

---

## API_DESIGN.md

包含：

```markdown
# API Design

## Endpoints / Operations

## Request Model

## Response Model

## Error Model

## Authentication

## Authorization

## Versioning

## Retry

## Idempotency
```

---

## UI_DESIGN.md

包含：

```markdown
# UI Design

## Screen Structure

## Component Structure

## Navigation

## State Management

## Interaction Design

## Responsive Strategy

## Accessibility

## Performance
```

---

## TECH_DECISIONS.md

包含：

```markdown
# Technical Decisions

## Decision

## Context

## Options

## Decision

## Reason

## Consequences

## Revisit Conditions
```

不得虚构任何技术决定。

---

# 11. 03_DECISIONS

DECISIONS.md 用于记录已经发生的重大决策。

必须包含：

```markdown
# Decisions

## Decision Record Format

### ID

### Date

### Context

### Decision

### Alternatives

### Reason

### Impact

### Status
```

状态至少支持：

```text
PROPOSED
APPROVED
REJECTED
SUPERSEDED
LOCKED
```

---

# 12. 04_CHANGES

## CHANGELOG.md

记录已经批准的变更。

包含：

```markdown
# Change Log

## Change Record

### ID

### Date

### Source

### Reason

### Affected Documents

### Affected Tasks

### Implementation Status

### Verification Status
```

---

## pending/

用于尚未批准的变更。

必须创建 `.gitkeep`。

---

# 13. 05_TASKS

## BACKLOG.md

包含：

```markdown
# Backlog

## Task Format

### ID

### Title

### Source Requirement

### Objective

### Scope

### Out of Scope

### Dependencies

### Acceptance Criteria

### Verification

### Status
```

---

## active/

创建 `.gitkeep`。

## completed/

创建 `.gitkeep`。

---

# 14. 06_TESTS

## TEST_STRATEGY.md

包含：

```markdown
# Test Strategy

## Testing Principles

## Unit Tests

## Integration Tests

## Acceptance Tests

## Regression Tests

## Test Data

## Failure Handling

## Release Criteria
```

其余四个目录创建 `.gitkeep`：

```text
unit/.gitkeep
integration/.gitkeep
acceptance/.gitkeep
regression/.gitkeep
```

---

# 15. 07_VERIFICATION

## VERIFICATION_RULES.md

包含：

```markdown
# Verification Rules

A task is verified only when:

1. Required implementation exists.
2. Required tests exist where applicable.
3. Tests pass.
4. Acceptance criteria pass.
5. Scope has not expanded.
6. Product behavior matches approved Spec.
7. Relevant state is updated.

## Verification Record

### Task ID

### Requirement

### Evidence

### Test Result

### Acceptance Result

### Scope Check

### Product Drift Check

### Final Result

PASS / FAIL / BLOCKED
```

创建：

```text
reports/.gitkeep
failures/.gitkeep
```

---

# 16. 08_STATE

## PROJECT_STATE.md

回答：

> 项目整体现在是什么状态？

包含：

```markdown
# Project State

## Current Phase

## Product Status

## Spec Status

## Design Status

## Implementation Status

## Test Status

## Verification Status

## Current Blockers

## Recent Decisions

## Next Task
```

---

## IMPLEMENTATION_STATE.md

回答：

> 代码现在做到哪里？

包含：

```markdown
# Implementation State

## Implemented

## Partially Implemented

## Not Implemented

## Known Technical Debt

## Current Build Status

## Current Test Status

## Next Implementation Task
```

---

## KNOWN_ISSUES.md

包含：

```markdown
# Known Issues

## Issue Format

### ID

### Description

### Impact

### Reproduction

### Current Status

### Workaround

### Related Task

### Related Decision
```

---

# 17. 09_AI

这是整个模板最重要的执行层。

---

## AI_RULES.md

必须包含以下原则：

```markdown
# AI Rules

## Rule 1 — Read Before Act

Before changing anything, AI must read:

1. PROJECT_CONTRACT.md
2. Relevant Product documents
3. Relevant Spec documents
4. Relevant Design documents
5. Current Project State
6. Current Task

## Rule 2 — Follow the Hierarchy

Product > Spec > Design > Task > Code

Implementation must not override higher-level intent.

## Rule 3 — No Scope Expansion

AI must not add functionality merely because it appears useful.

## Rule 4 — No Product Decisions

AI may make technical decisions within approved boundaries.

AI may not make unresolved product decisions.

## Rule 5 — Small Changes

Prefer the smallest change that satisfies the Task.

## Rule 6 — Evidence

Do not claim something is complete without evidence.

## Rule 7 — Update State

After meaningful work, update the relevant state documents.

## Rule 8 — Stop on Ambiguity

Do not guess when ambiguity affects product behavior.

## Rule 9 — Preserve Traceability

Every implementation task should be traceable to an approved requirement.

## Rule 10 — No Silent Changes

Do not silently modify Product, Spec, or locked Design documents.
```

---

# 18. WORKFLOW.md

必须规定 AI 每次工作的固定流程：

```text
1. READ
2. UNDERSTAND
3. CHECK STATE
4. IDENTIFY TASK
5. CHECK SCOPE
6. PLAN
7. IMPLEMENT
8. TEST
9. VERIFY
10. UPDATE STATE
11. REPORT
```

详细要求：

## READ

读取相关上下文。

## UNDERSTAND

明确：

- 当前目标
- 输入
- 输出
- 约束
- Acceptance Criteria

## CHECK STATE

确认当前项目状态。

## IDENTIFY TASK

确认当前 Task。

没有 Task 时：

> 不得自行创造大型功能任务。

## CHECK SCOPE

确认修改不会越界。

## PLAN

先形成简短实施计划。

## IMPLEMENT

只实现当前 Task。

## TEST

执行相关测试。

## VERIFY

检查：

- 功能
- Spec
- Scope
- Product Drift

## UPDATE STATE

更新状态。

## REPORT

报告：

```text
Completed
Tests
Verification
Files Changed
Remaining Issues
```

---

# 19. SPEC_RULES.md

必须明确：

```markdown
# Spec Rules

## Spec is a Contract

Spec defines required product behavior.

## AI May

- Clarify technical implementation.
- Identify contradictions.
- Propose missing details.
- Propose alternatives.

## AI May Not

- Change approved behavior.
- Remove constraints.
- Add product behavior without approval.

## Conflict Handling

If two Specs conflict:

STOP.

Do not choose one silently.

Report:

- Conflict
- Affected behavior
- Possible resolutions
```

---

# 20. TASK_RULES.md

必须明确：

```markdown
# Task Rules

A Task must have:

- ID
- Objective
- Source Requirement
- Scope
- Out of Scope
- Acceptance Criteria
- Verification Method

## Task Size

Prefer small, independently verifiable Tasks.

## Task Boundary

One Task should have one clear objective.

## Completion

A Task is not complete merely because code was written.

It requires verification.
```

---

# 21. CHANGE_RULES.md

必须规定产品变更流程：

```text
Change Request
      ↓
Impact Analysis
      ↓
Human Decision
      ↓
Update Product / Spec
      ↓
Update Design
      ↓
Create / Update Tasks
      ↓
Implementation
      ↓
Test
      ↓
Verification
```

必须明确：

> AI 可以提出 Change Proposal，但不能自行批准产品变更。

---

# 22. VERIFICATION_RULES.md

与 07_VERIFICATION/VERIFICATION_RULES.md 保持一致。

重点检查：

```text
Implementation Correctness
+
Spec Compliance
+
Acceptance Criteria
+
Scope Compliance
+
Product Drift
+
State Consistency
```

不能只检查“代码能不能运行”。

---

# 23. 99_FUTURE/IDEAS.md

包含：

```markdown
# Future Ideas

> Ideas in this file are NOT approved requirements.

## Idea Format

### ID

### Idea

### Motivation

### Possible Value

### Notes

### Status
```

状态：

```text
IDEA
CONSIDERING
REJECTED
APPROVED
```

关键规则：

> AI 不得因为 Future Ideas 中存在某个想法而实现它。

---

# 24. 模板文档的统一规则

所有模板 Markdown 必须：

1. 使用英文文件名。
2. 使用 Markdown。
3. 标题清晰。
4. 不写具体项目名称。
5. 不写具体技术栈。
6. 不写虚构数据。
7. 不写已经完成的功能。
8. 使用 `[PLACEHOLDER]` 表示未来由项目填写的内容。
9. 不使用模糊的“以后再说”代替明确状态。
10. 不在模板中加入与 Harness 无关的内容。

---

# 25. 特别禁止

Agent 在执行过程中禁止产生：

```text
src/
app/
pages/
components/
server/
backend/
frontend/
database/
```

等具体产品代码目录。

本任务只创建 Harness。

---

# 26. 不允许自行优化目录

即使 Agent 认为下面这些目录“更好”：

```text
10_MEMORY/
11_AGENTS/
12_AUTOMATION/
13_MCP/
14_KNOWLEDGE/
```

也不得创建。

如果认为确实需要：

记录为：

```text
Proposal:
Reason:
```

然后停止等待 Human。

---

# 27. 执行检查清单

完成后逐项检查。

## Directory Check

确认以下目录全部存在：

```text
00_PRODUCT
01_SPEC
02_DESIGN
03_DECISIONS
04_CHANGES
05_TASKS
06_TESTS
07_VERIFICATION
08_STATE
09_AI
99_FUTURE
```

## File Check

确认所有要求的 `.md` 文件存在。

## Placeholder Check

检查是否存在：

- 未关闭的 TODO
- 随意生成的示例产品
- 虚构技术方案
- 虚构需求

## Governance Check

确认：

- Human 是产品决策者。
- AI 是工程执行者。
- AI 不得扩大 Scope。
- AI 不得自行做产品决策。
- AI 遇到歧义必须停止。
- Future 不等于 Requirement。
- Task 不等于 Product Decision。

## Structural Check

确认：

```text
Product
↓
Spec
↓
Design
↓
Task
↓
Implementation
↓
Test
↓
Verification
↓
State
```

逻辑没有被破坏。

---

# 28. 最终报告格式

执行完成后，只需要报告：

```markdown
# Harness Creation Report

## Result

PASS / PARTIAL / BLOCKED

## Created Directories

[list]

## Created Files

[list]

## Validation

- Directory structure: PASS/FAIL
- Required files: PASS/FAIL
- Governance rules: PASS/FAIL
- Placeholder check: PASS/FAIL
- Product-specific content check: PASS/FAIL

## Problems

[None or list]

## Decisions Needed

[None or list]

## Notes

[Short notes]
```

不要写长篇解释。

---

# 29. 最终验收标准

只有同时满足以下条件才算 PASS：

```text
目录完整
+
文件完整
+
文件名称正确
+
核心规则存在
+
没有具体产品代码
+
没有擅自加入技术栈
+
没有擅自增加治理层
+
没有虚构产品需求
+
Human / AI 权限边界明确
+
Change 流程明确
+
Task 流程明确
+
Verification 流程明确
+
State 流程明确
```

任何一项失败：

```text
PARTIAL
```

如果遇到无法自行判断的问题：

```text
BLOCKED
```

---

# 30. 最重要的一句话

**你不是来设计这个系统的。**

**你是来按照这份计划把模板原样建立出来的。**

如果你认为计划可以改进：

```text
停止修改
↓
记录建议
↓
报告 Human
```

不要自行改变。

