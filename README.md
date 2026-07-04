# Virtual Company Workflow｜虚拟公司协作工作流

一个面向 AI Coding 和智能体协作的轻量级工作流模板。它的目标不是做一个复杂的“公司模拟器”，而是让 AI 在做项目时更像一个小型产品团队：先理解需求，再拆解方案，最后按开发、测试、复盘的节奏推进。

这个 Skill 可以用于 Codex、Claude Code，也可以复制到其他支持自定义规则或项目说明的 Agent 工具中使用。

## 适合用来做什么

- 从 0 到 1 搭建一个小工具、小网站或 AI 应用
- 把一个模糊想法整理成清晰的产品需求
- 让 AI 在写代码前先做产品分析、架构设计和任务拆解
- 在 vibe coding 时减少“想到哪写到哪”的混乱感
- 让不同角色视角参与项目，例如产品、设计、开发、测试和 Review

## 核心思路

主 Agent 充当项目负责人，根据项目阶段调用不同的虚拟角色：

| 角色 | 作用 |
|---|---|
| 用户代表 | 站在真实使用者角度，判断需求是否有价值、是否容易使用 |
| 产品经理 | 整理目标、功能边界、MVP 和优先级 |
| 设计师 | 思考页面结构、交互流程和用户体验 |
| 架构师 | 设计技术方案、模块边界、数据流和风险点 |
| 开发者 | 按任务实现代码，尽量保持可维护和可运行 |
| QA 测试 | 检查功能、边界条件、异常情况和回归风险 |
| Reviewer | 做最终审查，指出遗漏、改进点和下一步建议 |

你不需要真的创建多个智能体。即使只有一个 Agent，也可以让它按这些角色顺序思考和输出。

## 两种使用模式

### 1. 单 Agent 模式

适合 Codex、Cursor、Claude Code、Trea 等常见 AI 编程工具。一个 Agent 会依次模拟多个角色，完成需求分析、方案设计、开发、测试和复盘。

### 2. 多 Agent / Subagent 模式

适合支持子智能体的工具。主 Agent 可以把产品分析、技术设计、测试检查等任务交给不同子 Agent 处理，再汇总结果。

## 安装方式

Skill 文件夹路径如下：

```text
skills/virtual-company-workflow/
```

### Codex

把整个 Skill 文件夹复制到 Codex 的 skills 目录：

```text
%USERPROFILE%\.codex\skills\virtual-company-workflow
```

然后在 Codex 中这样使用：

```text
使用 $virtual-company-workflow，把这个项目按一个小型产品团队的方式推进。
```

或者：

```text
Use $virtual-company-workflow to run this project like a small product team.
```

### Claude Code

把 Skill 文件夹复制到以下任意位置：

```text
~/.claude/skills/virtual-company-workflow
```

或放到当前项目目录：

```text
.claude/skills/virtual-company-workflow
```

然后对 Claude Code 说：

```text
请使用 virtual-company-workflow skill 来推进这个项目。
```

### 其他 Agent 工具

如果你的工具不支持 Skill 系统，可以直接把下面这个文件的内容复制到系统提示词、项目规则或自定义说明里：

```text
skills/virtual-company-workflow/SKILL.md
```

`references/` 目录里的文件只在需要时再加载，不建议一开始全部塞进上下文，避免浪费 token。

## 推荐使用流程

### 第一步：先让 Agent 理解需求

```text
使用 virtual-company-workflow。
先从用户代表和产品经理视角分析这个想法，帮我整理 MVP，不要马上写代码。
```

### 第二步：确认方案后再做技术设计

```text
我认可这个 MVP。接下来请从架构师视角设计技术方案，包括目录结构、核心模块、数据流和风险点。
```

### 第三步：拆任务并开始实现

```text
请把开发任务拆成 3-5 个阶段，每个阶段完成后都做一次自检，再继续下一步。
```

### 第四步：让 QA 和 Reviewer 检查

```text
现在请切换到 QA 和 Reviewer 视角，检查功能是否完整、代码是否有明显问题，以及还有哪些可以优化。
```

## 示例：做一个习惯打卡工具

```text
使用 $virtual-company-workflow，帮我做一个简单的习惯打卡工具。
先让用户代表和产品经理分析需求，然后总结 MVP 给我确认。
我确认后，再继续设计技术方案并实现。
```

可能的推进节奏：

1. 用户代表：明确目标用户和使用场景。
2. 产品经理：确定 MVP，例如习惯创建、每日打卡、连续天数统计。
3. 设计师：设计首页、添加习惯页、统计区域。
4. 架构师：确定前端状态管理、本地存储和组件划分。
5. 开发者：实现页面和逻辑。
6. QA：测试新增、打卡、刷新、异常输入。
7. Reviewer：总结问题，给出下一步优化建议。

## 适合我的 vibe coding 用法

如果你想快速搭建 AI 应用，可以这样说：

```text
使用 virtual-company-workflow。
我想通过 vibe coding 快速做一个 AI 工具，请你先不要急着写代码。
先帮我从产品经理、架构师、开发者三个角度拆解需求，明确 MVP、技术栈、页面结构和接口设计。
```

如果你已经有代码仓库，可以这样说：

```text
使用 virtual-company-workflow。
请先阅读当前项目结构，从 Reviewer 和架构师角度判断项目现在的问题，然后给我一份优先级明确的修改计划。
```

如果你想接入模型 API，可以这样说：

```text
使用 virtual-company-workflow。
我要给这个项目接入 OpenAI 兼容接口，请先设计 Base URL、API Key、模型名称、请求转发和错误处理方案，再开始改代码。
```

## 设计原则

- 先想清楚，再写代码
- 先做 MVP，再做扩展
- 先保证能跑，再追求优雅
- 每一步都要有产出，不做空泛角色扮演
- 角色视角是为了提高质量，不是为了增加复杂度
- 遇到不确定的地方，要先列出假设和风险

## 不适合的情况

这个工作流不适合用来做大型组织模拟，也不适合让 AI 长篇大论地扮演角色。它更适合实际项目推进，尤其是 AI Coding、原型开发、工具搭建和项目重构。

## 项目目标

让 AI 像一个靠谱的小型产品团队一样工作：

- 能理解真实需求
- 能提出合理方案
- 能拆解任务
- 能写代码
- 能测试和复盘
- 能在项目过程中不断修正方向

简单说，它是一个让 vibe coding 更有章法的协作工作流。