# Happy Figure Skill

The paper is clear. The figure is still stuck.

You may have collected dozens of prompt templates, but most of them break as soon as the field, figure type, or target model changes.

The real bottleneck is not writing one more prompt. It is connecting research logic, figure structure, domain visual language, and model constraints into one reusable workflow.

**`happy-figure-skill` is built for the gap between research content and controllable scientific drawing prompts.**

It is not a prompt-template dump or a magic phrase for image models. It is an AI-agent workflow for reading research content, choosing the right figure type and domain visual language, controlling visible labels, respecting factual boundaries, and producing one copyable prompt for an image model.

It only generates drawing prompts. It does not generate images, replace scientific judgment, or decide publication compliance for the author.

## What It Helps With

Use this skill when:

- a paper has an abstract, methods section, or figure caption, but no clear graphical abstract direction.
- mechanism diagrams, roadmaps, apparatus schematics, or model architecture figures keep turning into generic "futuristic science art."
- figures from different fields get mixed up, such as CS papers being drawn like biomedical pathway diagrams.
- a reference figure has a useful style, but the style needs to be transferred without copying its scientific content.
- the research field is too specific for existing templates and needs an adaptive domain master.
- an agent should generate prompts from research material instead of rebuilding the figure logic from scratch every time.

The skill is especially useful when a generic prompt would flatten the research into vague visual decoration and lose the actual structure of the work.

## Core Idea

Instead of asking an image model to improvise from a loose description, `happy-figure-skill` breaks scientific visual prompting into a set of controllable decisions:

| Stage | Question | What the skill does |
| --- | --- | --- |
| Content reading | What is the research really about? | Extracts core context from PDF, Word, LaTeX, Markdown, captions, proposal material, or pasted text |
| Domain choice | What visual language fits this field? | Separates CS/ML, materials/chemistry, biology/medicine, and adaptive unknown-domain cases |
| Figure type | What kind of figure is needed? | Applies layout and communication rules for roadmaps, mechanisms, systems, comparisons, graphical abstracts, and overviews |
| Model adaptation | How should the prompt fit the target model? | Adds light constraints for Nano Banana Pro, Nano Banana 2, Qwen-image-2.0, gpt-image-2, and similar models |
| Text control | What text may appear in the figure? | Embeds visible-text restrictions directly into the final prompt |

This turns prompt writing from a one-off guess into a reusable scientific communication workflow.

## Usage

Ask an agent that supports skills to use it on a paper, document path, or pasted research section:

```text
Use $happy-figure-skill to read this paper and generate a graphical abstract prompt for Nano Banana Pro.
```

Or specify the figure goal directly:

```text
Use $happy-figure-skill to turn this methods section into a model architecture diagram prompt with English labels.
```

If the input is a LaTeX project folder, the agent should ask for the main `.tex` file instead of guessing the entry point. That small constraint prevents the workflow from reading the wrong file as the paper body.

## Output

By default, the skill may output:

- document understanding
- source basis
- one final drawing prompt ready to copy
- a short review reminder

When the style choice would materially affect the result, the skill should first output a short output-expectation confirmation with 2-3 options, then generate the final prompt after the user chooses.

If the user asks for only the prompt, the agent should output only the final drawing prompt.

## Post-Processing Notes

After using the final prompt to generate an image, do not treat the raw AI output as a publication-ready final figure. For formal submission, long-term maintenance, or repeated editing, use the generated image as a composition reference and move into manual redraw or vector reconstruction.

Common paths include:

- Redraw the structure in PPT, Figma, or Visio for flowcharts, system architecture diagrams, and logic-heavy schematics.
- Use Illustrator or Vectorizer for basic vectorization, then manually clean paths, relayout text, and unify line weights.
- For rule-based graphics, rebuild the figure with code such as Matplotlib so the final output is fully controllable.

This skill turns research content into high-quality drawing prompts. The author remains responsible for checking, editing, and reconstructing the final image for publication, attribution, copyright, and factual accuracy.

## Boundary

Scientific figures are not only about looking polished.

For real data charts, microscopy images, experimental photos, and quantitative evidence, an image model should not invent, repair, or rewrite factual content. This skill is best suited for qualitative schematics, mechanism explanations, method diagrams, graphical abstracts, and presentation-style research visuals.

In short: it helps translate research logic into visual instructions, but the researcher still owns the scientific judgment.
