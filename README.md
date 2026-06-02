# Happy Figure Skill

把论文内容变成可控、可检查、可复制的科研绘图提示词。

`happy-figure-skill` 是 [Happy Figure](https://github.com/datawhalechina/happy-figure) 的配套 Agent Skill。它面向中文科研用户，帮助你从论文摘要、方法段、图注、研究方案或开题材料中提取绘图逻辑，并生成适合 Nano Banana Pro、Qwen Image、gpt-image 等模型使用的结构化 prompt。

它不直接生成图片，也不替代作者判断科学事实。它做的事情更聚焦：**帮你把“这篇论文该怎么画”整理成一段更稳、更清楚、更容易交给绘图模型执行的提示词。**

## 为什么用它

- 论文逻辑很清楚，但不知道怎么转成图形摘要或机制图。
- 写出来的 prompt 太泛，成图总像“科技感海报”，不像学术插图。
- 计算机、材料、生物医学等不同领域的图示语言容易混在一起。
- 想让 Agent 先读论文内容，再给出可复制的绘图 prompt，而不是每次从零拆图。
- 想减少乱加文字、编造结构、箭头关系不清等常见翻车问题。

## 安装

### 方式一：npx 安装

直接使用 `npx skills add` 安装：

```bash
npx skills add BAIKEMARK/happy-figure-skill
```

安装完成后，默认调用名是：

```text
$happy-figure-skill
```

### 方式二：让 Agent 帮你安装

你也可以把下面这段话直接发给支持 shell 的 Agent：

```text
帮我安装 Happy Figure Agent Skill：

1. 从 GitHub 克隆 BAIKEMARK/happy-figure-skill。
2. 按照 Codex/Claude Skills 的本地规范安装这个 Skill。
3. 安装完成后检查目录中是否包含 SKILL.md、README.md、references/ 和 scripts/。
4. 给我一条可以直接测试的调用示例。
```

## 快速使用

```text
使用 $happy-figure-skill，读取下面这段论文摘要，生成一个适合 Nano Banana Pro 的图形摘要 prompt。
```

指定图类型：

```text
使用 $happy-figure-skill，根据这段 methods 生成一个技术路线图 prompt，图中文字只保留英文短标签。
```

指定领域风格：

```text
使用 $happy-figure-skill，把这段材料化学机制描述转成 Nature Materials 风格的机制示意图 prompt。
```

只要最终 prompt：

```text
使用 $happy-figure-skill，只输出最终绘图 prompt，不要解释过程。
```

## 适合场景

| 场景 | 你可以让它做什么 |
| --- | --- |
| 图形摘要 / 论文主图 | 从摘要或全文中提炼核心贡献，生成主视觉 prompt |
| 技术路线图 / 研究流程图 | 把研究步骤、模块关系和输出路径整理成流程图 prompt |
| 模型架构图 | 为 CS/ML 论文生成模块、输入输出和信息流描述 |
| 材料 / 化学机制图 | 把反应路径、微观结构、界面机制转成可绘制结构 |
| 生物医学机制图 | 梳理细胞、分子、通路、干预关系和可见标签 |
| 开题 / 答辩 / 组会总览图 | 把研究问题、技术路线和预期结果整理成汇报图 prompt |

## 注意边界

- 它适合生成定性示意图、机制图、方法框架图、图形摘要和展示型科研图。
- 它不适合让模型编造真实数据图、显微图、实验照片、定量曲线或统计显著性。
- 生成图片后，正式投稿前仍建议人工校对科学结构、文字标签和箭头关系。
- 对于投稿正文图，建议把 AI 输出作为构图参考，再进行人工重绘、矢量化或重新排字。

## 后续处理建议

拿到最终 prompt 并生成图片后，不建议直接把 AI 输出图当作论文终稿。对于正式投稿、长期维护或需要反复修改的插图，建议将生成结果作为构图参考，再进入人工重绘或矢量化重构阶段。

常见路径包括：

- 用 PPT、Figma、Visio 等工具参考重绘结构，适合流程图、系统架构图和逻辑关系明确的示意图。
- 用 Illustrator、Vectorizer 等工具做基础矢量化，再人工清理路径、重排文字和统一线条。
- 对规则性强的图形，可以参考生成结果，用 Matplotlib 等代码方式重建可控矢量图。

这个 Skill 负责把科研内容转化为高质量绘图 prompt；最终图像是否符合投稿、署名、版权和事实准确性要求，仍需要作者完成检查、编辑和重构。

## 和 Happy Figure 教程的关系

Happy Figure 教程讲方法论：如何理解科研绘图、如何设计提示词、如何控图、如何处理学术合规。

`happy-figure-skill` 则把这套方法变成 Agent 可以直接调用的工作流：读论文内容，判断图类型，选择领域视觉语言，生成可复制的绘图 prompt。

教程负责让你理解为什么这样画；Skill 负责帮你更快开始画。
