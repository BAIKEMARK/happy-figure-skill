# 科研绘图提示词汇总

## 1. Attention Is All You Need

### 提示词内容

```text
Generate a clean NeurIPS-style technical route map for the paper “Attention Is All You Need”. The figure should be a rigorous computer science / machine learning research schematic, not a decorative poster. Use a white background, soft tech pastel colors, thin clean outlines, rounded rectangles, light dashed grouping boxes, precise data-flow arrows, and readable sans-serif labels. The visual treatment should be a Strict Conference Paper Figure: clear, restrained, publication-friendly, with no heavy 3D, no glossy marketing style, no biomedical or materials-science visual language.

Overall layout: a left-to-right technical route map with four connected zones.

ZONE 1, left side, problem and input preparation:
Show the starting task as sequence transduction. Draw a horizontal stream of small token blocks entering the pipeline. The token blocks flow into token embedding, then merge with positional encoding represented as a subtle sinusoidal stripe or positional grid. Make clear that positional encoding is added because the model has no recurrence and no convolution.

ZONE 2, center-left, encoder route:
Draw a vertical stacked module labeled Encoder Stack N=6. Inside the stack, show repeated sublayers in order: Multi-Head Self-Attention, Add & Norm, Feed Forward Network, Add & Norm. Use a light blue container for the encoder. Draw residual skip arcs around the attention and feed-forward sublayers. The encoder outputs a compact set of encoded representations.

ZONE 3, center-right, decoder route:
Draw a parallel vertical stacked module labeled Decoder Stack N=6. Use a light lavender container for the decoder. Show input from Output Tokens shifted right entering the decoder. Inside the decoder, show Masked Self-Attention, Add & Norm, Encoder-Decoder Attention, Add & Norm, Feed Forward Network, Add & Norm. Draw a strong arrow from Encoded Representations into Encoder-Decoder Attention. Draw a mask symbol or small triangular blocked future-token indicator inside Masked Self-Attention. The decoder flows to Linear + Softmax and then to Predicted Tokens.

ZONE 4, upper or lower center breakout, attention mechanism:
Add a small inset panel connected by dashed arrows to both the encoder self-attention and decoder attention modules. In this inset, show Scaled Dot-Product Attention as Q, K, V streams entering a compact attention block, producing weighted values. Beside it, show Multi-Head Attention as several parallel attention heads, then Concat + Linear. Keep this inset schematic and readable, not formula-heavy.

ZONE 5, bottom band, training, evaluation, and contribution:
Create a bottom route band with three compact blocks: Training, Evaluation, and Advantages. Under Training, show WMT 2014 EN-DE, WMT 2014 EN-FR, Adam + Warmup, and Dropout + Label Smoothing as small clean chips. Under Evaluation, show BLEU and Constituency Parsing. Under Advantages, show No Recurrence, No Convolution, Parallelizable, and Short Dependency Paths. Connect the main Transformer architecture down to this bottom band using thin arrows, indicating that the architecture is trained and evaluated on translation and parsing tasks.

Connection rules:
1. Main flow must go from Input Tokens to Token Embedding plus Positional Encoding, then to Encoder Stack N=6, then to Encoded Representations.
2. Encoded Representations must connect into the Decoder Stack N=6 through Encoder-Decoder Attention.
3. Output Tokens shifted right must enter the decoder from the lower-left side of the decoder path.
4. Decoder Stack N=6 must flow to Linear + Softmax and then Predicted Tokens / Translation Output.
5. The Scaled Dot-Product Attention and Parallel Attention Heads inset must be visually linked to the attention sublayers, but must not interrupt the main route.
6. The bottom Training / Evaluation / Advantages band must support the method route, not dominate the figure.

All visible text in the figure must use only the following exact labels:
1. "Transformer Technical Route Map"
2. "Sequence Transduction"
3. "Input Tokens"
4. "Token Embedding"
5. "Positional Encoding"
6. "Encoder Stack N=6"
7. "Multi-Head Self-Attention"
8. "Add & Norm"
9. "Feed Forward Network"
10. "Encoded Representations"
11. "Output Tokens shifted right"
12. "Decoder Stack N=6"
13. "Masked Self-Attention"
14. "Encoder-Decoder Attention"
15. "Linear + Softmax"
16. "Predicted Tokens"
17. "Translation Output"
18. "Scaled Dot-Product Attention"
19. "Q"
20. "K"
21. "V"
22. "Parallel Attention Heads"
23. "Concat + Linear"
24. "Training"
25. "WMT 2014 EN-DE"
26. "WMT 2014 EN-FR"
27. "Adam + Warmup"
28. "Dropout + Label Smoothing"
29. "Evaluation"
30. "BLEU"
31. "Constituency Parsing"
32. "Advantages"
33. "No Recurrence"
34. "No Convolution"
35. "Parallelizable"
36. "Short Dependency Paths"

Do not render any title, legend, paragraph, footnote, random text, equation, citation, author name, email address, table, chart, axis, color bar, or structural field outside this list. Internal words such as “ZONE”, “layout”, “container”, or “connection” are only prompt instructions and must not appear in the rendered figure.

Strictly follow the specified scientific structure. Do not add, remove, merge, reorder, or reinterpret any scientific module. Do not invent quantitative data, values, curves, legends, color bars, equations, experimental results, or measurement labels. Do not draw the original paper figures verbatim; create a new technical route map based on the paper’s method. No marketing poster style, no decorative icons, no watermark.
```

---

## 2. Lithium solvation and anion-dominated domain structure in water-in-salt electrolytes

### 提示词内容

```text
Generate a professional materials chemistry mechanism schematic for a water-in-salt LiNTf2 electrolyte, based on the paper “Lithium solvation and anion-dominated domain structure in water-in-salt electrolytes”. The figure should be a high-fidelity academic mechanism diagram suitable for a materials chemistry or electrochemical energy storage paper. Use a clean white background, strict 2D vector scientific illustration, thin outlines, soft low-saturation colors, molecular ball-and-stick motifs, semi-transparent domain regions, and clear directional arrows. Do not use photorealism, glossy 3D, cartoon batteries, marketing poster style, or decorative icons.

Overall composition: a horizontal mechanism figure with four connected zones, moving from bulk electrolyte nanostructure to local solvation and finally to a simplified electrode interface. The scientific focus must be Li+ solvation, anion-rich domain, disrupted water network, and the electrode interface context.

ZONE 1, left side, bulk water-in-salt electrolyte nanostructure:
Draw a dense LiNTf2 water-in-salt electrolyte as a nanoscale heterogeneous liquid. Show a continuous blue-violet mesh-like region representing a percolating anion-rich domain made of NTf2 anions. The anion-rich domain should look like narrow but connected channels extending through the liquid. Inside and around this mesh, show small isolated pale-cyan water-rich domains as broken narrow pockets or short filaments, not a continuous water channel. Place red Li+ ions at the boundaries and inside both domains. The water-rich regions must become visually smaller and fragmented relative to the dominant anion-rich domain.

ZONE 2, upper center, Li+ solvation zoom-in:
Create a circular zoom-in inset from the boundary between the water-rich and anion-rich domains. Show one red Li+ ion in the center. Around it, place fewer H2O molecules with oxygen atoms oriented toward Li+, and several NTf2 oxygen atoms coordinating to Li+. Use dashed coordination lines from Li+ to water oxygen and from Li+ to NTf2 oxygen. Make the visual message clear: Li+ is solvated by both water and NTf2 anions, and anion coordination increases in concentrated water-in-salt electrolyte. Do not show Li+ as solvated only by water.

ZONE 3, lower center, disrupted water network:
Create a second zoom-in inset focused on the water network. Show a small cluster of H2O molecules with some remaining hydrogen bonds as thin blue dashed lines, but make the network incomplete and distorted. Include a red Li+ ion bridging two water oxygens to represent an O-Li-O bridge. Show broken or shortened hydrogen-bond chains to indicate that the extended pure-water hydrogen-bond network is disrupted. Do not draw a bulk-like continuous water network.

ZONE 4, right side, electrode interface context:
Draw a simplified flat electrode surface as a dark graphite-gray vertical slab at the far right. Next to it, draw a thin, generic passivating interphase layer without specifying chemical composition. Bring the same bulk electrolyte nanostructure toward the interface: anion-rich domain touching the interfacial region, isolated water pockets nearby, and Li+ ions moving through mixed water/anion environments toward the electrode. Use a restrained arrow showing Li+ transport across the electrolyte/interphase direction. Make the interface schematic generic and context-based, because the paper does not directly determine detailed SEI chemistry.

Visual encoding:
- Li+ ions: small red spheres.
- H2O molecules: red oxygen with two small white hydrogens, or simplified pale-cyan water molecule icons.
- NTf2 anions: blue-violet molecular ions, with SO2/O coordination sites near Li+ and hydrophobic CF3 regions forming the anion-rich domain.
- Anion-rich domain: semi-transparent blue-violet connected mesh or channel network.
- Water-rich domain: pale-cyan isolated pockets or narrow broken filaments.
- Coordination: thin purple dashed lines.
- Hydrogen bonds: thin light-blue dashed lines.
- Li+ transport: red curved arrow.
- Electrode: flat dark gray slab with a thin muted interphase layer.

All visible text in the figure must use only the following exact English labels:
1. "Water-in-salt electrolyte"
2. "LiNTf2"
3. "Anion-rich domain"
4. "Percolating anion network"
5. "Small isolated water-rich domains"
6. "Li+"
7. "H2O"
8. "NTf2 anion"
9. "Li+ solvation"
10. "Li-Owater"
11. "Li-ONTf2"
12. "Mixed water / anion coordination"
13. "Disrupted water network"
14. "Hydrogen bonds"
15. "O-Li-O bridge"
16. "Electrode interface"
17. "Generic interphase"
18. "Li+ transport"

Do not render any title, legend, paragraph, footnote, random text, concentration value, equation, coordinate axis, color bar, figure number, citation, author name, DOI, or structural field outside this list. Internal layout words such as “ZONE”, “inset”, “left side”, “right side”, or “visual encoding” are prompt instructions only and must not appear as visible text inside the rendered figure.

Scientific constraints:
Strictly follow the specified mechanism. Do not invent quantitative data, curves, experimental spectra, RDF plots, scattering profiles, exact SEI composition, electrode reaction products, gas evolution, battery performance values, or unsupported interfacial chemistry. Do not show water-rich domains as percolating continuous channels. Do not show Li+ solvated solely by water. Do not show anion-rich domains as isolated clusters only; they should appear extended and percolating. Do not imply that the paper directly measured detailed electrode-interface chemistry; the electrode interface must remain a simplified contextual schematic connected to the bulk electrolyte structure.
```

---

## 3. A foundation model for the Earth system

### 提示词内容

```text
Generate a professional system architecture diagram for the paper “A foundation model for the Earth system”. The figure should explain how Earth system variables are encoded into the Aurora foundation model, adapted for multi-task prediction, and used for weather and climate-related applications. Use a clean academic AI-system schematic style: white background, soft blue-green scientific palette, thin outlines, rounded rectangles, layered data cards, gridded globe/map motifs, atmospheric vertical-level stacks, and precise arrows. The figure should look like a high-quality Nature / machine-learning architecture figure, not a marketing poster, dashboard collage, or decorative climate illustration.

Overall layout: a left-to-right system architecture pipeline with five connected zones: heterogeneous Earth system inputs, universal latent foundation model, task adaptation, multi-task prediction heads, and downstream weather/climate applications.

ZONE 1, left side, Earth system variables:
Show multiple stacked geophysical data cards entering the system. Each card should be a small gridded map or vertical atmospheric slice. Include surface variables, atmospheric variables, ocean variables, wave variables, air-quality variables, and climate/reanalysis data as separate but visually aligned inputs. Use different soft colors for atmosphere, ocean, chemistry, waves, and land-surface context. Show that inputs may have heterogeneous spatial resolution, pressure levels, lead times, and variable sets, but keep the labels short.

ZONE 2, center-left, flexible encoder:
Draw a module labeled “3D Perceiver Encoder” receiving the heterogeneous data cards. The encoder should convert different variables, pressure levels, and resolutions into a common 3D latent representation. Visualize this as arrows from differently shaped input cards converging into a uniform translucent 3D cube or layered atmospheric volume.

ZONE 3, center, Aurora foundation model:
Place the largest central module labeled “Aurora Foundation Model”. Inside it, show a core processor labeled “3D Swin Transformer” with stacked latent blocks and local-window attention tiles. Add a small side adapter labeled “LoRA Adaptation” attached to the core, indicating efficient fine-tuning. Show recursive time evolution with a curved arrow from model output back into model input to represent autoregressive forecasting from time t to time t+1 and longer lead times. The central module should be the visual focus.

ZONE 4, center-right, multi-task prediction:
Draw a decoder module labeled “3D Perceiver Decoder” that maps the latent representation back to physical variables. From it, branch into four prediction heads: Air Quality, Ocean Waves, Cyclone Tracks, and High-Resolution Weather. Each head should be a compact output card with a small domain-specific visual cue: pollutant plume for air quality, wave field for ocean waves, cyclone spiral/track line for hurricanes, and gridded weather map for high-resolution weather. Keep the output heads parallel and clearly connected to the same foundation model.

ZONE 5, right side, weather and climate applications:
Show a final application panel receiving outputs from all prediction heads. Include concise application cards for Early Warning, Disaster Risk, Energy Planning, Agriculture, and Climate Services. Use thin arrows from the prediction heads to this application panel to show how multi-task forecasts support real-world weather and climate applications.

Connection rules:
1. Earth System Variables must flow into 3D Perceiver Encoder.
2. 3D Perceiver Encoder must produce a Universal Latent State.
3. Universal Latent State must enter Aurora Foundation Model / 3D Swin Transformer.
4. Aurora Foundation Model must connect to LoRA Adaptation for task-specific fine-tuning.
5. Aurora Foundation Model must connect to 3D Perceiver Decoder.
6. 3D Perceiver Decoder must branch into Air Quality, Ocean Waves, Cyclone Tracks, and High-Resolution Weather.
7. All prediction heads must connect to Weather / Climate Applications.
8. Include a curved feedback arrow indicating Recursive Forecasting from Time t+1 back to the next input step.

All visible text in the figure must use only the following exact English labels:
1. "Earth System Variables"
2. "Surface"
3. "Atmosphere"
4. "Ocean"
5. "Waves"
6. "Air Quality"
7. "Climate Data"
8. "Variable Resolution"
9. "Pressure Levels"
10. "3D Perceiver Encoder"
11. "Universal Latent State"
12. "Aurora Foundation Model"
13. "3D Swin Transformer"
14. "LoRA Adaptation"
15. "Recursive Forecasting"
16. "Time t"
17. "Time t+1"
18. "3D Perceiver Decoder"
19. "Multi-task Prediction"
20. "Air Quality Forecast"
21. "Ocean Wave Forecast"
22. "Cyclone Track Forecast"
23. "High-Resolution Weather"
24. "Weather / Climate Applications"
25. "Early Warning"
26. "Disaster Risk"
27. "Energy Planning"
28. "Agriculture"
29. "Climate Services"

Do not render any title, legend, paragraph, footnote, random text, author names, DOI, institutional names, equations, tables, scorecards, numerical performance values, axes, color bars, or structural field outside this list. Internal layout words such as “ZONE”, “left side”, “center”, “output heads”, or “connection rules” are prompt instructions only and must not appear as visible text inside the rendered figure.

Scientific constraints:
Strictly follow the specified architecture and relationships. Do not invent new model components, unsupported Earth system variables, performance metrics, benchmark numbers, agency comparisons, or physical mechanisms. Do not draw a generic chatbot or language-model diagram. Do not make the foundation model look like a cloud service dashboard. Preserve the central idea: heterogeneous Earth system variables are encoded into a universal latent representation, processed by an Aurora foundation model, fine-tuned/adapted for multiple forecasting tasks, and used for weather and climate applications.
```

---

## 4. Mechanisms of Ferroptosis and Relations With Regulated Cell Death: A Review

### 提示词内容

```text
生成一张专业的生物医学机制图，主题为“Mechanisms of Ferroptosis and Relations With Regulated Cell Death”。图像应为 Cell / Nature 风格的 BioRender-like 医学插画，干净白色背景，16:9 横向构图，高分辨率，矢量感，柔和医学配色，细胞质环境为浅蓝或浅灰半透明背景，细胞膜位于上方作为边界。整体目标是用一张机制总览图解释：铁依赖性脂质 ROS 累积如何导致 ferroptosis，以及 GPX4-GSH 轴、system x_c^-、PUFA 脂质氧化、Fenton reaction、铁稳态、ferritinophagy 和其他 RCD 通路之间的关系。请使用圆润有机的生物分子、膜结构、蛋白质团块、小分子胶囊、脂质双层、线粒体和自噬溶酶体样结构，不要使用抽象商业流程框，不要画成普通信息图。

构图分为 5 个内部区域，区域标题仅用于提示词结构，不要作为图中文字出现。

ZONE 1：上方细胞膜与 cystine-glutamate transport  
在图上方绘制一段横向细胞膜脂质双层，右上方嵌入一个粉紫色跨膜转运体 system x_c^-。膜外侧显示 Cystine 和 Glutamate，膜内侧显示 Cysteine 和 Glutamate。用绿色箭头表示正常 cystine 输入和 glutamate 输出。旁边放置橙色小分子 Erastin，用红色平头抑制线指向 system x_c^-，表示 Erastin 抑制 cystine uptake。由 Cysteine 向下连接到 GSH synthesis 模块，显示 Cysteine、Glutamate、Glycine 汇合生成 GSH。

ZONE 2：右侧 GPX4-GSH 抗氧化轴失效  
在右侧中部绘制 GSH、GSSG、GPX4 和 Lipid hydroperoxides 的还原通路。GPX4 画成绿色或青色折叠蛋白，GSH 作为小分子簇。用绿色箭头表示 GPX4 + GSH 将 Lipid hydroperoxides 还原为 Lipid alcohols。用红色平头抑制线表示 RSL3 直接抑制 GPX4；用蓝紫色小分子 FIN56 连接到 GPX4 degradation；用绿色小分子 FINO2 连接到 lipid peroxidation 和 GPX4 inactivation。显示当 GPX4-GSH 轴失效时，Lipid ROS 累积增强。

ZONE 3：左侧 PUFA-PE 脂质过氧化形成路径  
在左侧中部绘制 PUFA、AA、AdA、ACSL4、LPCAT3、LOXs 等脂质代谢模块。AA / AdA 以脂肪酸链图标表示，ACSL4 和 LPCAT3 以酶蛋白形态表示。用绿色箭头表示 AA / AdA 经 ACSL4 与 LPCAT3 酯化进入膜磷脂，形成 PUFA-PE 或 AA-PE。再由 LOXs 或 lipid autoxidation 促进生成 AA-OOH-PE / lipid hydroperoxides。旁边加入 Fe2+ 小球和 Fenton reaction，用橙红色箭头表示铁促进 ROS 生成。该区域的箭头应汇入中央 Lipid ROS。

ZONE 4：中心核心结局 Ferroptosis  
画面中央放置一个醒目的绿色到红色渐变圆形或发光分子云，标注 Lipid ROS，周围有少量过氧化脂质链和氧自由基符号作为视觉元素。由 Lipid ROS 向下连接到一个正在发生铁死亡的细胞：细胞体收缩，线粒体变小、膜密度升高、嵴减少，但不要画成凋亡小体或坏死破裂。最终向下用粗绿色或红色箭头指向 Ferroptosis。箭头语义必须清晰：绿色箭头表示促进或生成，红色平头线表示抑制，虚线表示转运或释放。

ZONE 5：下方铁稳态与其他调控性细胞死亡关系  
在下方左侧绘制铁稳态模块：Transferrin receptor、Fe3+、Fe2+、DMT1、Ferritin、NCOA4、Ferritinophagy、Lysosome。用虚线箭头表示铁摄取、储存和 ferritinophagy 释放游离 Fe2+；Fe2+ 再用箭头连接到 Fenton reaction 和 Lipid ROS。下方右侧绘制一个简洁的关系网络，显示 ferroptosis 与 Apoptosis、Necroptosis、Oxytosis、Autophagy/Ferritinophagy 存在联系但机制不同。用细灰色连接线连接，不要画成完全相同的死亡方式。可放置小型线粒体、自噬体和细胞死亡图标作为辅助视觉，但不要新增论文未描述的信号通路。

图中所有可见文字只能使用以下内容，不得出现任何额外英文、中文、标题、脚注、作者、DOI、期刊名、参考文献、随机缩写或未列出的标签：  
“Ferroptosis”  
“Lipid ROS”  
“Lipid hydroperoxides”  
“Lipid alcohols”  
“PUFA”  
“AA”  
“AdA”  
“AA-PE”  
“AA-OOH-PE”  
“ACSL4”  
“LPCAT3”  
“LOXs”  
“Lipid autoxidation”  
“Fenton reaction”  
“Fe2+”  
“Fe3+”  
“system x_c^-”  
“Cystine”  
“Cysteine”  
“Glutamate”  
“Glycine”  
“GSH”  
“GSSG”  
“GPX4”  
“Erastin”  
“RSL3”  
“FIN56”  
“FINO2”  
“GPX4 degradation”  
“Transferrin receptor”  
“DMT1”  
“Ferritin”  
“NCOA4”  
“Ferritinophagy”  
“Lysosome”  
“Apoptosis”  
“Necroptosis”  
“Oxytosis”  
“Autophagy”

请严格遵守科学边界：不要加入未提供的药物、基因、数值、显著性标记、实验曲线、患者图像、显微照片或具体疾病治疗结论；不要把 ferroptosis 画成 apoptosis 或 necrosis；不要让线粒体破裂成为主要结局；不要把 p53、p62-NRF2 等争议或双重调节机制画成确定主通路，除非另做独立分图。整体视觉应清楚表达“铁依赖性脂质过氧化物累积 + GPX4-GSH 防御失效 = ferroptosis”的核心逻辑，同时保留铁稳态和其他 RCD 关系作为辅助模块。内部结构词如 ZONE、layout、container、connections 只是提示词组织方式，不能出现在最终图片中。
```

5. Docs2KG 

```text
   Create a publication-ready computer science system architecture diagram for the paper “Docs2KG: A Human-LLM Collaborative Approach to Unified Knowledge Graph Construction from Heterogeneous Documents”.
   
     The figure should follow the visual style of a high-quality ACM WWW / KDD / SIGMOD / VLDB paper: clean modular pipeline, precise data-flow arrows, readable system components, knowledge graph abstraction, controlled labels, white background, low-saturation academic colors, and
     clear left-to-right narrative flow. Do not use Nature, Science, Cell Press, BioRender, biomedical mechanism, or materials-science illustration styles.
   
     Target image model: gpt-image-2 or another strong text-rendering model. Use an information-rich but controlled label strategy. Labels may be moderately numerous because the figure needs to explain the full workflow clearly.
   
     Overall layout:
     Use a wide horizontal 16:9 or 21:9 composition. The main flow should read from left to right:
   
     Heterogeneous enterprise documents → Document digitization → Multifaceted KG construction → Unified knowledge graph → Human-in-the-loop quality assurance → Downstream applications.
   
     Use a secondary feedback loop from human quality assurance back to KG construction to emphasize iterative expert refinement.
   
     Style:
     - Clean white or very light gray background.
     - Professional ACM-style technical vector illustration.
     - Soft pastel zones with very low saturation.
     - Rounded rectangular modules with thin gray outlines.
     - Clear solid arrows for main data flow.
     - Dashed arrows for auxiliary verification or feedback flow.
     - Knowledge graph nodes should be clean, abstract, and readable.
     - Use subtle depth only for document stacks, graph panels, or interface cards.
     - Avoid heavy 3D, glossy effects, cartoon style, marketing poster style, dramatic shadows, or decorative icons.
   
     Main visual structure:
   
     ZONE 1 — Input Documents, far left:
     Show a compact stack of heterogeneous enterprise document sources. Include simplified icons for PDF files, scanned reports, tables, figures, and web pages. These should look like abstract document cards, not real screenshots.
   
     Visible labels in this zone:
     - "Heterogeneous Documents"
     - "PDF Reports"
     - "Scanned Files"
     - "Tables"
     - "Figures"
     - "Web Pages"
   
     ZONE 2 — Document Digitization, left-center:
     Create a large rounded module labeled "Document Digitization". Inside it, show two parallel paths:
     1. A native digital document processing path.
     2. An OCR path for scanned documents.
   
     Both paths should produce standardized extracted elements: text, tables, figures, and layout elements. Use small document parser, OCR scan beam, table extraction, and layout block icons.
   
     Visible labels in this zone:
     - "Document Digitization"
     - "Native Digital Path"
     - "OCR Path"
     - "Text"
     - "Layout Elements"
   
     ZONE 3 — Multifaceted KG Construction, center:
     Create three stacked horizontal construction streams. Each stream should have a distinct soft color and clear boundary.
   
     Top stream: MetadataKG.
     Show document property cards and metadata nodes connected to source documents. Represent filenames, authorship, temporal attributes, spatial attributes, and provenance as small property nodes.
   
     Visible labels:
     - "MetadataKG"
     - "Document Properties"
     - "Source Provenance"
     - "Temporal Attributes"
     - "Spatial Attributes"
   
     Middle stream: LayoutKG.
     Show a document hierarchy tree: document → page → section → paragraph → table / figure. Use nested blocks and hierarchy edges.
   
     Visible labels:
     - "LayoutKG"
     - "Document Hierarchy"
     - "Sections"
     - "Paragraphs"
     - "Tables and Figures"
   
     Bottom stream: SemanticKG.
     Show a modular semantic extraction pipeline. It should contain three sub-pathways that converge into an entity-relation graph:
     1. Ontology-driven extraction.
     2. Entity-list-driven extraction.
     3. LLM-assisted ontology generation.
   
     Represent entities, relations, events, causal relations, and domain concepts as connected graph nodes.
   
     Visible labels:
     - "SemanticKG"
     - "Ontology-driven Extraction"
     - "Entity-list-driven Extraction"
     - "LLM-assisted Ontology Generation"
     - "Entities"
     - "Relations"
     - "Events"
     - "Causal Relations"
     - "Domain Concepts"
   
     ZONE 4 — Unified Knowledge Graph, right-center:
     Create a large integrated graph panel. It should merge three visual layers: metadata, layout, and semantic knowledge. Use three node families with distinct but soft colors. The graph should be visually rich but not dense or unreadable.
   
     The panel should clearly communicate that the final graph preserves document provenance, document structure, and semantic relationships.
   
     Visible labels:
     - "Unified Knowledge Graph"
     - "Metadata Layer"
     - "Layout Layer"
     - "Semantic Layer"
     - "Cross-domain KG"
   
     ZONE 5 — Human-in-the-loop Quality Assurance, bottom-right or lower band:
     Create an annotation and review workspace connected to the unified graph. Show a human expert or reviewer icon examining graph nodes and edges on a clean interface card. Show expert editing of entities and relations, plus quality evaluation metrics.
   
     Use a dashed or curved feedback arrow from this module back to the KG construction streams, especially the SemanticKG stream.
   
     Visible labels:
     - "Human-in-the-loop QA"
     - "Expert Annotation"
     - "Entity Editing"
     - "Relation Editing"
     - "Quality Evaluation"
     - "Human-LLM Opinion Distance"
     - "Contribution Score"
     - "Retention Rate"
     - "Iterative Refinement"
   
     ZONE 6 — Downstream Applications, far right:
     Create a final compact application panel receiving the refined unified knowledge graph. Show three clean application cards: knowledge retrieval, grounded question answering, and enterprise knowledge management.
   
     Visible labels:
     - "Downstream Applications"
     - "Knowledge Retrieval"
     - "Grounded QA"
     - "Enterprise Knowledge Management"
   
     Connections:
     1. Draw a solid main arrow from "Heterogeneous Documents" to "Document Digitization".
     2. Inside "Document Digitization", show two parallel lanes: "Native Digital Path" and "OCR Path".
     3. Draw arrows from digitized elements into "MetadataKG", "LayoutKG", and "SemanticKG".
     4. Inside "SemanticKG", show three internal branches: "Ontology-driven Extraction", "Entity-list-driven Extraction", and "LLM-assisted Ontology Generation".
     5. Draw converging arrows from "MetadataKG", "LayoutKG", and "SemanticKG" into "Unified Knowledge Graph".
     6. Draw a validation arrow from "Unified Knowledge Graph" to "Human-in-the-loop QA".
     7. Draw a curved dashed feedback arrow from "Human-in-the-loop QA" back to the KG construction streams.
     8. Draw a final arrow from "Unified Knowledge Graph" to "Downstream Applications".
     9. Avoid crossing arrows. Keep the flow readable and logically ordered.
   
     All visible text in the figure must use only the following exact English labels:
     1. "Heterogeneous Documents"
     2. "PDF Reports"
     3. "Scanned Files"
     4. "Tables"
     5. "Figures"
     6. "Web Pages"
     7. "Document Digitization"
     8. "Native Digital Path"
     9. "OCR Path"
     10. "Text"
     11. "Layout Elements"
     12. "MetadataKG"
     13. "Document Properties"
     14. "Source Provenance"
     15. "Temporal Attributes"
     16. "Spatial Attributes"
     17. "LayoutKG"
     18. "Document Hierarchy"
     19. "Sections"
     20. "Paragraphs"
     21. "Tables and Figures"
     22. "SemanticKG"
     23. "Ontology-driven Extraction"
     24. "Entity-list-driven Extraction"
     25. "LLM-assisted Ontology Generation"
     26. "Entities"
     27. "Relations"
     28. "Events"
     29. "Causal Relations"
     30. "Domain Concepts"
     31. "Unified Knowledge Graph"
     32. "Metadata Layer"
     33. "Layout Layer"
     34. "Semantic Layer"
     35. "Cross-domain KG"
     36. "Human-in-the-loop QA"
     37. "Expert Annotation"
     38. "Entity Editing"
     39. "Relation Editing"
     40. "Quality Evaluation"
     41. "Human-LLM Opinion Distance"
     42. "Contribution Score"
     43. "Retention Rate"
     44. "Iterative Refinement"
     45. "Downstream Applications"
     46. "Knowledge Retrieval"
     47. "Grounded QA"
     48. "Enterprise Knowledge Management"
   
     Do not render any title, legend, paragraph, footnote, author name, paper title, conference name, random text, formula, number, table value, fake UI text, or structural field outside this list.
   
     Do not invent quantitative data, experimental results, curves, charts, icons with unreadable labels, or screenshots from the original paper. This should be a redesigned academic system schematic, not a reproduction of the paper’s original figure.
   
     The final figure should look like a polished ACM WWW / KDD / VLDB / SIGMOD-style system framework diagram: modular, readable, technically precise, and suitable for a computer science paper.
```

   
