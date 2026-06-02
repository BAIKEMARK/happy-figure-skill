# Figure Type Fusion Contracts

This file is not a set of copy-paste long prompt masters. It is an internal figure-type adapter for the Skill. Do not concatenate this file with domain masters verbatim.

Fusion principles:
- Domain masters control scientific objects, domain semantics, publication community, and Stage 2 rendering language.
- Figure-type rules only constrain communication goal, layout candidates, region organization, connection logic, visible labels, and common failure modes.
- If a domain master conflicts with a figure-type rule, priority is: scientific facts > explicit user requirements > domain master > figure-type structure > model adaptation > aesthetic wording.
- The final prompt must include visible-text restrictions and scientific boundaries. It must not invite the drawing model to invent data, devices, mechanisms, or experimental results.

Recommended internal Figure Brief fields:
1. Image goal: one sentence explaining what the figure helps the reader understand.
2. Domain objects: concrete visual entities and terminology from the selected domain master.
3. Figure-type structure: layout, regions, and connection rules from this file.
4. Visible text: complete list of labels allowed in the image.
5. Scientific boundaries: what cannot be added, invented, or misdrawn.
6. Final drawing prompt: one copyable prompt fused from domain master, figure-type contract, model adaptation, and language strategy.

## 1. Technical roadmap / research workflow

Purpose: Show research steps, method path, and output relationship.

Use for: Methods, research plan, thesis proposal route, model/experiment workflow, data-processing workflow.

Layout candidates:
- Horizontal main flow for linear methods.
- Vertical flow for stage-by-stage progress or presentation pages.
- Three-part flow: problem/input -> method/analysis -> output/validation.
- Layered workflow when submodules sit under a main path.

Must extract:
- Research starting point or problem background.
- 3-6 key steps.
- Final output, validation target, or conclusion direction.
- Arrow direction, branch, feedback, or parallel relationship.

Visible text:
- Step names, module names, input/output short labels.
- Do not generate long explanations, random legends, unlisted titles, or footnotes.

Common failures:
- Becoming decorative flow boxes without domain objects.
- Adding steps not supported by the paper.
- Drifting into a graphical abstract or mechanism diagram.
- Reversing arrow direction.

Fusion rule:
- Domain master decides how the domain objects inside each step are represented.
- This type only enforces step progression and readable path logic.

## 2. Experimental system / apparatus schematic

Purpose: Show which real components compose the experimental system and how they connect.

Use for: Experimental platform, instrument structure, reactor/sensor/acquisition systems, device relationships in testing workflows.

Layout candidates:
- Central apparatus plus surrounding function modules.
- Input side -> central reaction/test zone -> output/acquisition side.
- Vertical zones: object / measurement system / data analysis.

Must extract:
- Experimental or test object.
- Real instruments, devices, sensors, reactors, acquisition modules, or system components.
- Material flow, gas flow, electrical signal, data flow, or sample-transfer relationship.
- Required and forbidden labels.

Visible text:
- Device names, module names, input/output short labels.
- Must come from the paper or user-provided description.

Common failures:
- Inventing devices, sensors, pipes, parameters, or manufacturing details.
- Becoming product advertising, photo-realistic equipment rendering, heavy metallic highlights, or complex mechanical cutaway.
- Overcrowded connections that look like a circuit board or engineering construction drawing.

Fusion rule:
- Domain master decides accurate representation of materials, samples, biological entities, or computing modules.
- This type only enforces real components, connection logic, and simplified academic schematic style.

## 3. Mechanism explanation diagram

Purpose: Explain how a phenomenon, reaction, regulation, or action path happens.

Use for: Mechanism, reaction pathway, regulatory pathway, material evolution, pathology/pharmacology, internal algorithmic effect relationships.

Layout candidates:
- Causal chain: A leads to B, B leads to C.
- Central object radiating to multiple factors.
- Multiscale zoom: macro object -> microstructure -> molecule/module.
- Comparative mechanism: before/after, normal/abnormal, method A/B.

Must extract:
- Core phenomenon or process to explain.
- Key entities and context/environment.
- Promotion, inhibition, migration, conversion, transfer, feedback, or related action semantics.
- Mechanistic boundaries supported by the paper.

Visible text:
- Key entity names, process names, action labels.
- Keep labels sparse and accurate.

Common failures:
- Inventing intermediate mechanisms, formulas, parameters, or results.
- Becoming a research workflow.
- Using dramatic effects instead of scientific relationships.
- Ambiguous arrows that mix activation, inhibition, and conversion.

Fusion rule:
- Domain master decides entity forms such as lattices, ions, cells, proteins, neural modules, or system components.
- This type only enforces mechanism path, arrow semantics, and scientific boundary.

## 4. Multi-panel comparison

Purpose: Compare differences across groups, conditions, methods, materials, or stages.

Use for: Result comparison, operating-condition comparison, ablation study, material/sample contrast, treatment vs control.

Layout candidates:
- 2x2 panels.
- Horizontal three- or four-panel strip.
- Upper/lower double row.
- Left condition key plus right uniform comparison panels.

Must extract:
- Comparison objects and group names.
- What each panel should show.
- Which contents are real data and which can only be qualitative schematic.
- Shared scale, viewpoint, color logic, legend, and margin rules.

Visible text:
- Panel letters, group names, necessary labels.
- Do not add coordinates, color bars, significance marks, or numeric values unless provided in the source.

Common failures:
- Each panel has a different style and loses comparability.
- Fabricating curves, significance marks, heatmap color bars, or axes.
- Becoming a graphical abstract or promotional collage.

Fusion rule:
- Domain master decides the domain-specific object or visual language inside each panel.
- This type only enforces uniform comparison structure and data boundaries.

## 5. Graphical abstract / main paper figure

Purpose: Compress the paper's problem, core method, key process, and main contribution into one figure.

Use for: Graphical Abstract, main paper figure, submission summary graphic, one-figure contribution summary.

Layout candidates:
- Problem -> method -> finding/contribution.
- Left-center-right narrative.
- Central finding radiating outward.
- 3-4 region summary composition.

Must extract:
- Research problem or pain point.
- Core method, material, model, or system.
- Key process, mechanism, or validation path.
- Main finding, contribution, or application value.

Visible text:
- Few short labels that support the main narrative.
- Avoid long sentences, paragraphs, and dense terminology.

Common failures:
- Stuffing all paper details into one figure.
- Becoming a plain workflow or single mechanism diagram.
- Becoming too promotional and losing scientific substance.
- Exaggerating contribution or inventing results.

Fusion rule:
- Domain master decides central visual object and disciplinary tone.
- This type only enforces the compressed "one figure explains the contribution" narrative.

## 6. Proposal / defense / presentation overview

Purpose: Summarize project structure, research modules, and presentation storyline.

Use for: Proposal cover slide, defense overview, group meeting first page, project framework.

Layout candidates:
- Central theme plus surrounding modules.
- Top/middle/bottom: background/problem -> research modules -> expected output.
- Left-to-right: problem -> route -> result.
- Module matrix for parallel research contents.

Must extract:
- Background and core problem.
- Research objective.
- 2-4 major research modules.
- Technical route, stage plan, or expected output.

Visible text:
- Short slide-readable headings.
- Avoid dense explanatory paragraphs.

Common failures:
- Becoming a commercial pitch deck, consulting framework, or decorative cover.
- Drawing planned work as completed conclusions.
- Confusing module hierarchy so the audience cannot understand the project structure quickly.

Fusion rule:
- Domain master decides the domain objects inside each module.
- This type only enforces overview hierarchy and presentation readability.

## 7. Journal cover art / Cover Art

Purpose: Turn the research highlight into a visual metaphor and strong cover image.

Use for: Journal cover, inside cover, paper promotion image, visual teaser.

Layout candidates:
- Vertical cover composition with one strong central subject.
- Central scientific object plus symbolic environment.
- Fusion of macroscopic scene and microscopic mechanism.
- Abstract visual metaphor while keeping the scientific object recognizable.

Must extract:
- Research object most suitable for cover treatment.
- Core mechanism, structure, life process, algorithmic concept, or application scene.
- Keywords that can become visual metaphors.
- Scientific boundaries that must not be misread through art direction.

Visible text:
- Default: no visible text.
- Never generate journal logo, masthead, issue number, barcode, author names, or real publication elements.

Common failures:
- Becoming an advertisement, fantasy scene, product poster, or fake journal cover.
- Over-artistic rendering that makes the scientific object unrecognizable.
- Presenting metaphor as experimental result.

Fusion rule:
- Cover art should not use ordinary white-background paper-figure Stage 2.
- Use cover-specific rendering: vertical format, strong focal subject, premium aesthetics, truthful scientific object and mechanism.
