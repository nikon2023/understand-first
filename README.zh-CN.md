# Understand First｜先理解，再回答

**先诊断问题，再回答。目标不是产出更多，而是看清规律、找到根因、完成验证，并把突破沉淀成可迁移能力。**

`understand-first` 是一个 Human–AI 问题解决 Skill。

它适合那些“给出一个看起来不错的答案”仍然不够的问题。

它要求 Human 与 AI 最终能够回答四件事：

1. **规律是什么？**
2. **根因是什么？**
3. **怎么验证？**
4. **下次能复用什么能力？**

## 核心闭环

```text
问题
 ↓
前置诊断
 ↓
回答 / 推理
 ↓
最低有效表达层级
 ↓
Evidence Gate
 ↓
能力候选
```

## 三个来源

这个 Skill 不是来自某一个人的完整方法。

它把三个相互独立的思想组合成一个可执行协议。

### 1. Reddit：回答前先诊断问题

Reddit 上广泛传播的一组 Prompt，要求 AI 在正式回答前先做四件事：

1. 找出用户没有明确说出的默认假设；
2. 找出可能实质改变答案的缺失信息；
3. 指出处理此类问题最常见的错误；
4. 只提出一个最关键的问题。

在本 Skill 中，这一段属于 **Canonical Preflight**。

默认不修改它的结构和目的。

它不是为了让回答更长。

它是为了减少 AI 很自信地回答错误问题的概率。

### 2. 陶哲轩：正确结果不等于人类真正理解

陶哲轩关于 AI 辅助数学工作的公开讨论提供了一个重要目标：

获得结果，不等于人类已经理解结果。

人类仍然需要判断、解释、连接和内化结果。

因此，本 Skill 把“是否真正理解”操作化为四项检查：

```text
规律
 ↓
根因
 ↓
验证
 ↓
迁移
```

这四项是本 Skill 的工程化提炼。

它不是陶哲轩的原话。

### 3. Karpathy：当文字成为瓶颈，就升级表达介质

Karpathy 提出了一条理解 LLM 输出的表达梯子：

```text
STE 风格文字
 ↓
结构图
 ↓
交互网页
 ↓
定制讲解视频
```

`understand-first` 把它作为 **Representation Ladder**。

默认从最低成本层级开始。

只有当前表达形式本身阻碍理解时，才升级一级。

不是每个问题都要生成四种成果。

## 运行原则

- 简单明确的问题 → 直接回答。
- 模糊、战略或分析型问题 → 执行 Canonical Preflight。
- 看不清结构 → 升级到结构图。
- 需要改变变量或比较状态 → 升级到交互模型。
- 需要理解时间变化和动态因果 → 升级到渐进式动态讲解。
- 结论会影响研究、工程、架构或长期规则 → 执行 Evidence Gate。
- 同类问题反复出现 → 尝试提取能力候选。

## 理解是否增加的判断标准

回答结束后，至少检查四件事。

1. **Pattern｜规律**：我现在是否能看见重复出现的结构？
2. **Root Cause｜根因**：我是否知道为什么会发生？
3. **Verification｜验证**：我是否知道如何检查这个判断？
4. **Transfer｜迁移**：下次遇到类似问题，我是否可以少依赖一次 AI？

如果四项都没有改善，那么即使结果很漂亮，也不能说明理解真正增加。

## 四级表达梯子

### L1｜文字降噪

默认使用简洁、低歧义的文字。

参考 ASD-STE100 的思想，但不声称获得正式 STE100 合规认证。

文字够用时停止。

### L2｜结构图

当问题核心是结构、层级、流程、因果、架构或状态关系时使用。

图必须揭示关系。

### L3｜交互网页

当理解依赖变量变化、状态切换、路径比较或反馈时使用。

HTML 只是实现手段。

交互必须回答一个明确问题。

### L4｜动态讲解

当核心困难来自时间过程、动态因果、空间变化或概念逐步构建时使用。

可以使用动画、视频和 TTS。

## Evidence Gate

表达清楚不代表结论正确。

重要内容应区分：

- Fact｜事实
- Supported Judgment｜有证据支持的判断
- Inference｜推断
- Assumption｜工作假设
- Unknown｜未知或尚未验证

表达介质升级时，不得自动升级结论置信度。

## 能力沉淀

如果一次问题解决暴露出可重复机制，使用：

```text
卡点
 ↓
根因
 ↓
解决机制
 ↓
验证方法
 ↓
迁移规则
```

得到的结果首先是 **Candidate Capability**。

不要因为一次成功就变成全局规则。

建议生命周期：

```text
Candidate
 ↓
Trial
 ↓
Evidence
 ↓
Review
 ↓
Adopt / Revise / Reject
```

## 推荐使用场景

适合系统架构、科研设计、根因分析、项目卡点、重复 Debug、复杂阅读、工作流改造、证据评审，以及可能沉淀成长期规则的决策。

不建议用于简单事实问答。

## 仓库结构

```text
understand-first/
├── SKILL.md
├── README.md
├── README.zh-CN.md
└── CHANGELOG.md
```

## 推荐调用方式

```text
Use understand-first on this problem.
```

或者：

```text
先理解，不要急着回答。用 understand-first 分析这个问题。
```

## 来源

- Reddit Prompt：
  https://www.reddit.com/r/PromptEngineering/comments/1rrhrh0/this_is_the_most_useful_thing_ive_found_for/
- Terence Tao × Dwarkesh Patel，*How the world's top mathematician uses AI*：
  https://www.youtube.com/watch?v=Q8Fkpi18QXU
- Andrej Karpathy，关于理解 LLM 输出的帖子：
  https://x.com/karpathy/status/2105819303471976479

## 来源边界

`understand-first` 是一个独立组合设计。

Reddit 提供前置诊断 Prompt。

陶哲轩的公开讨论提供“正确输出不等于理解”的目标启发。

Karpathy 提供表达介质升级梯子。

Evidence Gate、能力迁移检查和 Candidate 生命周期属于本 Skill 的组合与扩展设计。

本项目与上述作者和平台不存在官方隶属或背书关系。
