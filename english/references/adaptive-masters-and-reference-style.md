# Adaptive Masters and Reference Style

Use this reference only when the user's request goes beyond the built-in domain masters or when the user provides a reference image/style target. It defines two separate modes:

1. **Unknown-domain adaptive master**: create a reusable domain master for a field not covered by `domain-masters.md`.
2. **Reference-image style supplement**: extract transferable style from a reference image and attach it to an existing master without copying scientific content.

## Mode A: Unknown-Domain Adaptive Master

Use this mode when the research field does not fit the existing CS/ML, materials/chemistry, or biology/medicine masters, especially for interdisciplinary or specialized fields such as environmental science, geology, energy systems, civil engineering, agriculture, ecology, psychology, education, public health, remote sensing, or policy modeling.

If the user also provides a reference image and the current model can inspect images, use it as a visual reference. If the current model cannot inspect images, ask the user to provide a short description of the image's layout, palette, icons, labels, and overall style before generating a new master.

### Source Logic

This mode combines:

- The custom meta-prompt idea: use a top-tier reference figure to infer field-specific layout and visual semantics.
- The new-domain master format: save the result as a complete reusable field master rather than a short style note.

### What To Infer

Infer only reusable field-level conventions:

- Typical research objects and visual entities.
- Common process logic or causal chains.
- Usual figure types in the field.
- Layout patterns and information hierarchy.
- Field-appropriate visual language, symbols, textures, scales, and metaphors.
- Typography, label density, and annotation habits.
- Accuracy, ethics, data, and evidence boundaries.

Do not copy:

- Specific scientific claims from the reference image.
- Data values, curves, maps, microscopy/photo evidence, measurements, labels, sample names, or experimental results.
- Logos, watermarks, proprietary templates, or distinctive copyrighted composition details.

### Output Format For A Newly Generated Master

```markdown
## New Domain Judgment
[Field name; why existing masters are insufficient; whether a reference image was used; what reusable field-level visual signals were inferred.]

## New Domain Master Draft

# [Field Name] Domain Master

## Suitable Scenarios
[Which figure types and research contexts this master covers.]

## Field-Specific Visual Conventions
[Objects, layouts, hierarchy, palette, symbols, arrows, scale cues, typography, and label density.]

## Stage 1: Visual Schema
[A complete schema-building prompt with role, objective, layout selector, field semantics, visual object rules, connection rules, and output format.]

## Stage 2: Rendering Prompt
[A complete render prompt with art style, layout execution, visual rules, {VISIBLE_TEXT_RULE}, and forbidden-content constraints.]

## Replaceable Variables
[Research topic, object list, stages, labels, figure type, target venue, model, language strategy.]

## Stable Constraints
[Constraints that should not be removed because they preserve scientific accuracy and visual consistency.]

## Quality Checklist
[8-10 checks for scientific structure, field semantics, visual consistency, labels, evidence boundaries, and target venue needs.]

## Final Drawing Prompt For This Request
[Use the new master draft to produce one ready-to-copy prompt for the user's current figure.]

## Save-As-Skill Option
If the user is satisfied, ask whether to save this domain master into `references/domain-masters.md` so future requests in this field can use it directly.
```

### Save Protocol

Only save the new domain master after the user explicitly approves it. When saving:

- Append a new `## [Field Name]` section to `references/domain-masters.md`.
- Preserve the same two-stage structure as existing domain masters.
- Keep `{VISIBLE_TEXT_RULE}` as a placeholder in Stage 2.
- Add or update an eval fixture if the new domain is likely to recur.
- If both English and Chinese skill versions exist, update both unless the user asks to update only one.

## Mode B: Reference-Image Style Supplement

Use this mode when the field already has a suitable master or figure-type master, but the user wants the output to resemble a provided reference image's style.

This mode produces a style supplement, not a new master by default.

### Image Capability Gate

- If the current model can inspect the uploaded image, analyze it directly.
- If it cannot inspect images, ask the user to describe the reference image or switch to a vision-capable model.
- Do not pretend to have inspected an image that is unavailable or unreadable.

### Analysis Dimensions

Extract transferable design properties:

1. Layout and composition: direction, stages, panel structure, focal center, whitespace.
2. Information hierarchy: primary/secondary modules, grouping, emphasis.
3. Containers and shapes: rectangles, rounded panels, organic forms, lattices, icons, callouts.
4. Lines and arrows: thickness, curvature, dashed/solid semantics, arrowhead style.
5. Color palette: hue families, saturation, contrast, background, grouping colors.
6. Typography and labels: font style, label density, placement, capitalization.
7. Texture and depth: flat vector, subtle shadows, isometric cues, paper/interface/material texture.
8. Field semantics: only if style-relevant; do not copy the reference figure's scientific content.

### Output Format

```markdown
## Reference Style Summary
[5-8 concise bullets describing transferable style features.]

## Reference Style Supplement
[One paragraph or compact block that can be appended to the selected master prompt. It should describe style, layout, palette, arrows, typography, and what to avoid.]

## Do Not Copy From Reference
[Specific content categories that must not transfer: labels, data, modules, result claims, logos, watermarks, exact composition.]

## Applicability Boundary
[What figure types this style fits or does not fit.]

## Final Drawing Prompt
[Selected master + user research content + reference style supplement + visible-text rule.]
```

### Integration Rule

The style supplement must never override scientific structure, visible-text restrictions, evidence boundaries, or model-specific label-density rules. The selected master remains the main prompt; the reference style supplement is an additive layer.
