---
name: happy-figure-skill
description: Use when the user wants a copyable AI prompt for scientific figures from research documents, pasted research text, figure captions, thesis or proposal material, or vision-readable reference images, including scientific illustrations, graphical abstracts, mechanism diagrams, model architecture diagrams, technical roadmaps, experimental setup schematics, multi-panel comparisons, presentation overviews, reference-style scientific figure prompts, or adaptive domain masters for uncovered fields.
---

# happy-figure-skill

Generate a copyable scientific drawing prompt from a research document, research text, or a vision-readable reference image. The skill does not generate images, call image models, recommend drawing tools, or provide post-processing workflows.

## Core workflow

1. Parse the research input.
   - If the user provided a file path, run `scripts/extract_research_doc.py`.
   - For `.docx`, `.pdf`, `.tex`, `.latex`, `.md`, and `.txt`, extract title, abstract, methods, results, captions, conclusion, and candidate context snippets. Legacy `.doc` can be attempted, but it depends on local conversion tools; if it fails, ask the user to convert it to `.docx` or paste the relevant text.
   - If the user points to a LaTeX folder, ask for the main `.tex` file path. Do not guess the entrypoint.
   - If parsing quality is weak, say so briefly and base the prompt only on visible, extracted text.

2. Infer the drawing context.
   - Identify the research topic, likely field, candidate figure type, and best paper section to visualize.
   - Prefer a field master when the research clearly matches CS/ML, materials/chemistry, or biology/medicine.
   - Field masters must use the publication context that matches the discipline: for computer science, prefer ACM/IEEE/NeurIPS/ICML/CVPR/ACL/VLDB/KDD/WWW-style architecture and system-diagram logic, not Nature/Science/Cell biomedical or materials-science visual language; use materials/chemistry or biology/medicine journal styles only for those fields.
   - For CS/ML papers, separate two decisions instead of treating them as one: **Content Community** (which research venue family best matches the topic and information organization) and **Visual Treatment** (whether the user wants a strict paper figure, premium academic graphical abstract, presentation/whitepaper overview, or minimal flat vector schematic).
   - If the user has not specified a target style, do not lock into a single style immediately; present 2-3 short "output expectation confirmation" candidates. Each candidate should name Content Community + Visual Treatment + what result it is best for, and mark the recommended option. The goal is to let the user confirm the paid image-generation direction quickly, not to make them read a long style explanation.
   - If the user mentions "beautiful", "premium", "texture", "polished", "teaser", "graphical abstract", "poster", "project page", or similar aesthetic goals, prefer a **Premium Academic Graphical Abstract** visual treatment over a plain conference-paper flowchart, while keeping the correct CS content community.
   - If the style choice would materially change the final prompt, ask the user to choose among the candidates first and do not output the final drawing prompt in the same response; proceed with the recommendation only when the user asks for a fast/default generation or prompt-only output.
   - Treat figure type as a communication contract, not as a replacement for the field master. When the field is clear, use the domain master as the primary scientific visual language and use `references/figure-type-masters.md` only as an adapter for communication goal, layout, regions, connections, visible labels, and failure modes.
   - Use figure-type rules alone only when the field is unclear, cross-disciplinary, or not covered and a generic structure is sufficient without losing important field-specific visual semantics.
   - If the field is not covered by the built-in domain masters and a generic figure-type master would lose important field-specific semantics, load `references/adaptive-masters-and-reference-style.md` and use **Mode A: Unknown-Domain Adaptive Master** to draft a new reusable domain master plus the current final drawing prompt.
   - If the user provides a reference image or asks to match a reference style, load `references/adaptive-masters-and-reference-style.md` and use **Mode B: Reference-Image Style Supplement**. Use it as an additive style layer, not a replacement for the selected or newly generated master.
   - Only inspect reference images when the current model has image-understanding capability. If the image is unavailable or the current model cannot inspect images, ask for a concise reference-image description instead of pretending to have seen it.
   - If multiple choices are plausible, recommend one and ask only the unresolved high-impact question.

3. Ask only necessary questions.
   Ask for missing choices only when they materially change the final prompt:
   - Figure type: roadmap, experimental setup, mechanism schematic, multi-panel comparison, graphical abstract, proposal/defense overview, or other.
   - Content focus: abstract, methods, results, figure caption, whole paper, proposal content, or a user-specified section.
   - Figure text language: Chinese, English, Chinese prompt with English labels, or minimal text.
   - Drawing model: ask only when the model choice would materially change prompt language, label density, or structural constraints; otherwise do not block generation and default to a gpt-image-2 / strong text-rendering model friendly generic version.

4. Load only the needed references.
   - Use `references/domain-masters.md` for CS/ML, materials/chemistry, biology/medicine.
   - Use `references/figure-type-masters.md` for figure-type fusion contracts: roadmap, experimental system, mechanism explanation, multi-panel comparison, graphical abstract, presentation overview, and cover art.
   - Use `references/model-cards.md` for model-specific light adaptation.
   - Use `references/language-strategy.md` for figure text language and the exact embedded visible-text rule.
   - Use `references/prompt-quality-check.md` for the short review reminder.
   - Use `references/adaptive-masters-and-reference-style.md` for unknown-domain master generation, reference-image style supplements, and save-as-skill protocol.

5. Build one final prompt.
   - Do not concatenate domain masters and figure-type rules verbatim.
   - Use the domain master as the primary scientific visual language whenever the domain is covered.
   - Use the figure-type contract as an adapter that constrains communication goal, layout, regions, connections, visible labels, scientific boundaries, and common failure modes.
   - Internally create a Figure Brief before writing the final prompt: image goal, domain objects, figure-type structure, regions/modules, connections, visible text, scientific boundaries, and model adaptation.
   - If domain and figure type conflict, use this priority: scientific facts > explicit user requirements > domain master > figure-type structure > model adaptation > aesthetic wording.
   - Keep model adaptation short. Do not override the domain visual language or scientific constraints.
   - If the user did not specify a model, default to a gpt-image-2 / strong text-rendering model friendly strategy: keep richer controlled labels that clarify the workflow instead of compressing to minimal text by default.
   - Put the visible-text restriction inside the final prompt, using the exact Chinese or English wording from `references/language-strategy.md`.
   - Replace `{VISIBLE_TEXT_RULE}` with the language-appropriate visible-text rule from `references/language-strategy.md`; do not leave `{VISIBLE_TEXT_RULE}` or any bracketed placeholder in the user-facing final prompt.
   - Treat Stage 1 Visual Schema blocks as internal planning. The final prompt may still use structured layout headings such as `ZONE 1`, `ZONE 2`, and `CONNECTIONS` to organize the drawing instruction, but it must not contain unfinished scaffolding such as `[Paste the full Visual Schema here]`, `[Insert extracted research context]`, `---BEGIN PROMPT---`, `---END PROMPT---`, or unfilled `[Label ...]` placeholders.
   - When structural headings such as `ZONE` are used in the final prompt, make clear through the visible-text rule that those headings are instruction structure only and must not be rendered as text inside the figure unless explicitly listed as visible labels.
   - If an adaptive domain master was drafted, output the new master draft and the final prompt separately. Ask whether the user wants to save the new domain master only after they confirm it is satisfactory.
   - If the user explicitly approves saving an adaptive domain master, append it to `references/domain-masters.md` and keep `{VISIBLE_TEXT_RULE}` as the Stage 2 placeholder. When both English and Chinese skill versions are present, update both unless the user asks for only one version.
   - Do not make visible figure text a separate action for the user.

## Output format

Use this structure in the user's language:

When output-expectation confirmation is needed, output only `## Document understanding`, `## Output expectation confirmation`, and the necessary `## Basis`, then wait for the user's choice. Only skip the wait and output the final prompt when the user asks for a fast/default generation or prompt-only output.

```markdown
## Document understanding
[3-6 bullets: topic, field, selected content focus, chosen figure type, drawing model, figure text language]

## Output expectation confirmation
[When the user has not specified a target style and style would materially affect paid image-generation results, list 2-3 short candidates. Each candidate should be no more than 2 lines and include Content Community + Visual Treatment + what result it is best for; mark the recommended option. Let the user choose direction quickly. Do not write a long style explanation.]

## Basis
[List the extracted sections or snippets used. Keep concise.]

## Adaptive domain master draft
[Output only when the field is not covered and a new domain master was created. Include suitable scenarios, field-specific visual conventions, Stage 1 Visual Schema, Stage 2 Rendering Prompt, replaceable variables, stable constraints, and quality checklist.]

## Reference style supplement
[Output only when a reference image/style is used. Include transferable style summary, additive prompt supplement, do-not-copy list, and applicability boundary.]

## Final drawing prompt
[One complete prompt that the user can copy directly into the drawing model. Include the visible-text restriction inside this prompt. All placeholders and internal schema handoff markers must be resolved before output.]

## Figure-text review checklist
[Do not output by default. Output only when there are many figure labels, the user asks to check labels, or terminology needs extra review. It must match the text already embedded in the final prompt.]

## Short review reminder
[One short reminder to review scientific accuracy, labels, data boundaries, and journal requirements; if the model is unspecified or richer labels are used by default, optionally mention that a minimal-text variant can be provided if needed.]
```

If the user only wants the prompt, output only `## Final drawing prompt`.

## Journal and factual-content handling

Do not block or refuse journal manuscript figures. Scientific manuscript figures are allowed as prompt-generation requests.

When the request involves journal submission, add only a concise review reminder. When it involves real data charts, microscopy images, experimental photos, or factual image repair, remind the user that the drawing model should not invent or alter factual evidence. Still keep the main output focused on prompt generation.

## Non-goals

Do not recommend or explain Excalidraw, draw.io, Figma, Illustrator, Vectorizer, Edit-Banana, Paper2Any, video tutorials, watermark removal, or vectorization workflows unless the user explicitly asks for those topics. This skill is only for generating scientific drawing prompts.
