# Happy Figure Skill

<p align="center">
  <a href="https://github.com/datawhalechina/happy-figure">
    <img src="https://raw.githubusercontent.com/datawhalechina/happy-figure/main/docs/media/banner.png" alt="Happy Figure" width="100%">
  </a>
</p>

<h3 align="center">🚀 把科研内容编译成可控、可校对、可复用的 AI 绘图 Prompt 💡</h3>

<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/BAIKEMARK/happy-figure-skill?style=for-the-badge&logo=github&label=Stars&logoColor=white&color=ffda65&cacheSeconds=300)](https://github.com/BAIKEMARK/happy-figure-skill/stargazers)
[![Happy Figure Tutorial](https://img.shields.io/badge/Happy%20Figure-Tutorial-6D5EF8?style=for-the-badge&logo=github&logoColor=white)](https://github.com/datawhalechina/happy-figure)
<a href="https://qm.qq.com/q/ZEfzKSQ5CW"><img alt="QQ reader group" src="https://img.shields.io/badge/QQ%20Group-Reader%20Community-12B7F5?style=for-the-badge&logo=qq&logoColor=white"></a>

</div>

<p align="center">
  简体中文 ｜
  <a href="README_EN.md">English</a> ｜
  <a href="#-快速开始">快速开始</a> ｜
  <a href="LICENSE">License</a>
</p>


把论文、图注、开题材料、研究方案和参考图，编译成可复制、可校对、可控的 AI 科研绘图 prompt。

`happy-figure-skill` 是 [Happy Figure](https://github.com/datawhalechina/happy-figure) 的 Agent Skill。它不直接生成图片，而是让 Claude Code / Codex 这类 Agent 先读懂科研内容，再按 **领域 x 图类型 x 绘图模型特性** 生成适合 Nano Banana Pro、Nano Banana 2、Qwen Image 2 / 2 Pro、GPT Image 2 等模型执行的结构化绘图提示词。

一句话：它不是“再给你一段万能 prompt”，而是一个面向科研插图的 **提示词路由器 + 图形结构编译器**。

## 🖼️ 先看效果

我们挑选了 5 类典型科研绘图任务交给 Happy Figure Skill，下面是用它生成的提示词分别在 5 个模型上跑出的结果。

这个 showcase 想先证明一件事：Happy Figure Skill 可以覆盖不同领域、不同图类型，而不是只会写某一种“科研风”提示词。顺带你也能看到，同一套 prompt 换到不同模型后，默认画风、文字稳定性和结构习惯会怎样分化。

- 它能把 CS/ML、材料化学、生物医学、地球科学等内容，整理成可执行的绘图 prompt。
- 它能让你按领域、图类型和模型特性选择更合适的出图路线。

<table>
  <tr>
    <th width="13%">任务</th>
    <th width="17%">Qwen Image 2</th>
    <th width="17%">Qwen Image 2 Pro</th>
    <th width="17%">Nano Banana 2</th>
    <th width="17%">Nano Banana Pro</th>
    <th width="17%">GPT Image 2</th>
  </tr>
  <tr>
    <td><b>CS/ML 架构图</b><br><sub>model architecture</sub></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/attention__qwen-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/attention__qwen-image-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/attention__qwen-image-2-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/attention__qwen-image-2-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/attention__nano-banana-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/attention__nano-banana-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/attention__nano-banana-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/attention__nano-banana-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/attention__gpt-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/attention__gpt-image-2.webp" width="160"></a></td>
  </tr>
  <tr>
    <td><b>文档智能流程图</b><br><sub>document pipeline / KG</sub></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/docs2kg__qwen-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/docs2kg__qwen-image-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/docs2kg__qwen-image-2-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/docs2kg__qwen-image-2-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/docs2kg__nano-banana-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/docs2kg__nano-banana-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/docs2kg__nano-banana-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/docs2kg__nano-banana-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/docs2kg__gpt-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/docs2kg__gpt-image-2.webp" width="160"></a></td>
  </tr>
  <tr>
    <td><b>材料化学机制图</b><br><sub>materials chemistry mechanism</sub></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/wis-lintf2__qwen-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/wis-lintf2__qwen-image-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/wis-lintf2__qwen-image-2-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/wis-lintf2__qwen-image-2-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/wis-lintf2__nano-banana-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/wis-lintf2__nano-banana-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/wis-lintf2__nano-banana-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/wis-lintf2__nano-banana-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/wis-lintf2__gpt-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/wis-lintf2__gpt-image-2.webp" width="160"></a></td>
  </tr>
  <tr>
    <td><b>生物医学机制图</b><br><sub>biomedicine mechanism</sub></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/ferroptosis-rcd__qwen-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/ferroptosis-rcd__qwen-image-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/ferroptosis-rcd__qwen-image-2-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/ferroptosis-rcd__qwen-image-2-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/ferroptosis-rcd__nano-banana-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/ferroptosis-rcd__nano-banana-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/ferroptosis-rcd__nano-banana-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/ferroptosis-rcd__nano-banana-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/ferroptosis-rcd__gpt-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/ferroptosis-rcd__gpt-image-2.webp" width="160"></a></td>
  </tr>
  <tr>
    <td><b>地球科学解释图</b><br><sub>earth science explanation</sub></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/earth-aurora__qwen-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/earth-aurora__qwen-image-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/earth-aurora__qwen-image-2-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/earth-aurora__qwen-image-2-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/earth-aurora__nano-banana-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/earth-aurora__nano-banana-2.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/earth-aurora__nano-banana-pro.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/earth-aurora__nano-banana-pro.webp" width="160"></a></td>
    <td align="center"><a href="https://github.com/BAIKEMARK/happy-figure-showcase-assets/blob/main/hd/earth-aurora__gpt-image-2.png"><img src="https://raw.githubusercontent.com/BAIKEMARK/happy-figure-showcase-assets/main/thumbs/earth-aurora__gpt-image-2.webp" width="160"></a></td>
  </tr>
</table>

> 🔎 完整提示词和 5 x 5 映射表放在 [showcase assets](https://github.com/BAIKEMARK/happy-figure-showcase-assets/tree/main/prompts) 里，主仓库只保留 Skill 本体。

> 💡 TIPS：同系列模型通常会保留相近的默认画风。Qwen 2 系列有独特的科研插图质感，适合低成本多抽卡，但复杂图可能破碎，文字越多错字率越高；Nano 系列更像平面科研插画，AI 味更明显，容易把 `ZONE` 这类结构词画进图里；GPT Image 2 的文字和结构更稳，画风更偏干净矢量底稿，和 Nano / Qwen 不是同一路线。

> ⚠️ Warning：这些图是模型输出示例，不是投稿终稿。正式发表前仍建议作者人工校对科学结构、图中文字、箭头关系、数据边界，并按期刊要求重绘、矢量化或重新排字。

## 🧭 它强在哪

普通提示词经常只会说“生成一张科研示意图”。Happy Figure Skill 会先做三层判断：

| 判断层 | 它会看什么 | 结果是什么 |
| --- | --- | --- |
| 研究领域 | CS/ML、材料化学、生物医学，或未知/交叉领域 | 选择对应领域母版，决定科学对象、期刊语境和视觉语言 |
| 图类型 | 技术路线图、实验系统图、机制图、多面板比较图、Graphical Abstract、汇报总览图、Cover Art | 约束布局、区域、箭头、面板、可见文字和失败边界 |
| 绘图模型 | Nano Banana Pro、Nano Banana 2、Qwen Image 2 / Pro、GPT Image 2 | 轻量适配标签密度、结构约束、审美目标和文字策略 |

这意味着你可以说：

```text
使用 $happy-figure-skill，读取这段 methods，生成一张材料化学机制解释图 prompt。
目标模型是 Nano Banana Pro，图中文字只保留英文短标签。
```

它不会把“材料机制图”写成通用流程图，也不会把“模型架构图”套成 Nature/Cell 生物医学风格。领域母版负责科学语义，图类型负责表达任务，模型卡负责最后的执行适配。

## 🎛️ 模型怎么选

这不是一个“哪个模型绝对最强”的排名。更准确的说法是：不同模型适合不同出图目标。

| 你更看重 | 优先尝试 | 原因 |
| --- | --- | --- |
| 高完成度 graphical abstract、第一眼质感 | Qwen Image 2 Pro、Nano Banana Pro | 更容易生成有层次、有设计感的科研主视觉 |
| 复杂结构稳定、最终候选稿 | Nano Banana Pro | 更适合多区域、强层级、箭头关系明确的结构图 |
| 多轮快速试图、找构图方向 | Nano Banana 2、Qwen Image 2 | 适合先跑多个候选，再挑结构和风格 |
| 中文或中英混排的风格候选稿 | Qwen Image 2、Qwen Image 2 Pro | 中文语义和科研术语理解友好，但图中文字要尽量少 |
| 模块关系清楚、文字较多、后期重绘底稿 | GPT Image 2 | 结构底稿、系统框架和 text-rich diagram 更可控，文字相对更稳 |

你也可以参考上面的 showcase，按各个模型的实际效果挑选适合自己的风格。如果还是不知道选哪个，先让 Skill 生成一版模型中性的结构化 prompt；等你拿到第一批图，再按“更漂亮 / 更清晰 / 更少文字 / 更像正文图 / 更像主视觉”继续改。

## 🧩 覆盖的图类型

| 图类型 | 适合内容 | Skill 会重点控制 |
| --- | --- | --- |
| 技术路线图 / 研究流程图 | methods、研究方案、开题技术路线、数据处理流程 | 步骤数量、阅读方向、分支/反馈、输入输出 |
| 实验系统 / 装置结构示意图 | 实验平台、仪器结构、采集系统、样品流转 | 真实部件、连接关系、物料流/信号流/数据流 |
| 机制解释图 | 反应路径、调控通路、材料演化、疾病机制 | 实体形态、因果链、促进/抑制/转化箭头 |
| 多面板比较图 | 对比实验、组别差异、消融、工况设置 | 面板统一性、尺度、组别名、数据边界 |
| 图形摘要 / 论文主图 | 论文核心贡献、项目主页图、投稿摘要图 | 研究问题、核心方法、关键过程、主视觉层级 |
| 开题 / 答辩 / 汇报总览图 | 课题结构、研究模块、预期成果、组会汇报 | 总览层级、模块关系、演示可读性 |
| 期刊封面图 / Cover Art | cover art、teaser、宣传主视觉 | 视觉隐喻、强中心对象、禁止伪造刊名/卷期/logo |

## 🌐 覆盖的领域

| 领域 | 典型视觉语言 | 适合任务 |
| --- | --- | --- |
| 计算机科学 / 机器学习 | ACM/IEEE/NeurIPS/ICML/CVPR/ACL 等论文图语境，模块、数据流、token、KG、pipeline、系统边界 | 模型架构图、LLM pipeline、知识图谱系统、信息检索、数据库、文档处理系统 |
| 材料与化学 | Nature Materials / Advanced Materials 风格，晶格、界面、离子迁移、溶剂化壳层、反应路径 | 电化学、催化、晶体/界面机制、多尺度材料结构、反应路径图 |
| 生物与医学 | BioRender / Cell / Nature 风格，细胞、蛋白、通路、组织微环境、药物作用机制 | 信号通路、疾病机制、临床流程、药物作用、细胞微环境 |
| 未知或交叉领域 | 自适应领域母版，从参考材料和领域语义生成新母版草案 | 地球科学、环境、能源系统、农业、心理学、公共卫生、政策建模等 |
| 参考图风格迁移 | 只抽取可迁移的布局、配色、线条、字体和层级，不复制科学内容 | “按这张图的风格画”，但保持本论文自己的科学结构 |

## ⚡ 快速开始

```bash
npx skills add BAIKEMARK/happy-figure-skill
```

安装后，在 Claude Code / Codex 里直接说：

```text
使用 $happy-figure-skill，读取下面这段论文摘要，生成一张适合 Nano Banana Pro 的图形摘要 prompt。
```

也可以把安装任务交给有 shell 权限的 Agent：

```text
帮我安装 Happy Figure Agent Skill：
1. 从 GitHub 克隆 BAIKEMARK/happy-figure-skill。
2. 按 Codex/Claude Skills 的本地规范安装这个 Skill。
3. 安装完成后检查目录中是否包含 SKILL.md、README.md、references/ 和 scripts/。
4. 给我一条可以直接测试的调用示例。
```

## 🧪 使用示例

指定图类型：

```text
使用 $happy-figure-skill，根据这段 methods 生成一个技术路线图 prompt。
图中文字只保留英文短标签，不要生成长句解释。
```

指定领域和期刊语境：

```text
使用 $happy-figure-skill，把这段材料化学机制描述转成 Nature Materials 风格的机制示意图 prompt。
目标模型是 Qwen Image 2 Pro。
```

指定模型特性：

```text
使用 $happy-figure-skill，基于这篇 CS/ML 论文生成模型架构图 prompt。
目标是 GPT Image 2，优先保证模块关系和较多文字标签清晰。
```

只要最终 prompt：

```text
使用 $happy-figure-skill，只输出最终绘图 prompt，不要解释过程。
```

使用文件：

```text
使用 $happy-figure-skill，读取 ./paper.pdf，提取摘要、方法、图注和结论，生成一张 Graphical Abstract prompt。
```

## 🔁 工作流

1. 读取科研内容：支持摘要、methods、图注、研究方案，也支持 `.pdf`、`.docx`、`.tex`、`.md`、`.txt` 等文件。
2. 形成 Figure Brief：判断研究主题、领域、图类型、目标模型、图中文字语言和科学边界。
3. 选择母版：领域母版决定科学对象和学科视觉语言，图类型母版决定表达任务和布局结构。
4. 适配模型：根据模型偏置调整标签密度、结构约束、文字策略和风格词强度。
5. 输出最终 prompt：包含可见文字白名单、禁止编造内容、箭头语义、区域结构和渲染风格。
6. 简短审查：提醒作者检查科学结构、标签、箭头、数据边界和期刊要求。

## 🚧 不做什么

这个 Skill 专注于“从科研文档生成绘图提示词”，因此它不会假装解决所有科研绘图问题。

| 不适合 | 原因 |
| --- | --- |
| 真实数据图、统计曲线、显著性标记 | 不能让图像模型编造数据、坐标、p 值或实验结果 |
| 显微图、实验照片、真实设备照片 | 这些属于证据图像，不应由生成模型伪造 |
| 需要严格几何尺寸或工程制图的图 | 生成图适合构图参考，不适合作为精确工程图 |
| 直接投稿原始 PNG | 投稿前仍需人工校对、重绘、矢量化或重新排字 |
| 去水印、仿真实期刊封面元素 | 不生成刊名、logo、卷期号、条形码等可能误导的出版物元素 |

## 📚 和 Happy Figure 教程的关系

Happy Figure 教程讲方法论，覆盖：如何理解科研绘图、如何设计提示词、如何控图、如何后处理 AI 生成的插图，以及如何处理学术合规。学懂 Happy Figure，你就能系统掌握可控、可校对、可发表级别的 AI 科研绘图流程。

`happy-figure-skill` 把其中“撰写科研绘图提示词”的方法变成了支持 Agent 调用的 Skill：读论文内容，判断图类型，选择领域视觉语言，适配模型特性，生成可复制的绘图 prompt。

教程负责让你理解为什么这样画；Skill 负责让你更快开始画。

## ⭐ Star 这个项目

如果它帮你把“我知道论文该画什么，但不知道怎么写成图像模型能执行的 prompt”这件事推进了一步，欢迎 Star。

接下来会继续补更多真实论文案例、更多领域母版、更多模型对比和更完整的科研绘图质量检查规则。

<a href="https://www.star-history.com/?repos=BAIKEMARK%2Fhappy-figure-skill&type=date&logscale=&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=BAIKEMARK/happy-figure-skill&type=date&theme=dark&logscale&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=BAIKEMARK/happy-figure-skill&type=date&logscale&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=BAIKEMARK/happy-figure-skill&type=date&logscale&legend=top-left" />
 </picture>
</a>

## License

This project is licensed under CC BY-NC-SA 4.0. See [LICENSE](LICENSE) for details.
