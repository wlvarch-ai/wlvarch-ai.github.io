---
title: "From sketch and card model to material preview"
date: 2026-03-01
author: David Heesom and Harrison Edis
summary: "Using iterative image prompting to test timber, glazing, planting and Victorian brick on a laser-cut model of a glazed infill gallery, without leaving the model's geometry behind."
tags: [showcase, concept design, physical model, image generation, materiality]
ai_disclosure: "The concept sketch and the physical model are the author's own, made by hand and by laser cutter. The material palette image and the three model renders were produced with Google Gemini image generation from text prompts and photographs of the model. No CAD or Photoshop work was done on the outputs."
---

AI image tools are most useful at concept stage when they work from something the designer has already made. This entry starts with a loose sketch and a laser-cut model and uses a series of prompts to turn them into a material preview of a glazed infill gallery between two Victorian buildings.

## Starting point

There were two inputs, both made before any AI tool was involved.

The first was a hand-drawn perspective sketch of an arched, glazed infill space joining an existing brick building, with planting climbing the arches and figures moving through it.

![Hand-drawn perspective sketch of a sequence of arches linking to existing brickwork, with green planting and people walking through]({{ '/assets/images/2026/sketch-and-model-to-material-preview/01-concept-sketch.jpg' | relative_url }})
*The concept sketch: fineliner and green marker.*

The second was a physical model in chipboard and laser-cut board, with a strip of clear acrylic for the glazing. It fixes the geometry, a row of five arched bays between two solid blocks, but says nothing about materials, texture or context.

![Laser-cut chipboard model of five arched bays over a clear acrylic strip, set between two solid blocks with loose roof planes]({{ '/assets/images/2026/sketch-and-model-to-material-preview/03-physical-model.jpg' | relative_url }})
*The physical model as photographed in the studio.*

The aim was to settle a material palette and then apply it to the model, exactly where the arches sit, to see how a contemporary infill might meet a Victorian brick building.

## Method

This was not a one-prompt result. It took a series of steps, each correcting the last.

**1. Material and atmosphere.** The first prompts set the palette on its own, away from the model. The brief was a calm, natural space: timber-framed arches, clear glazing open to the sky, neatly maintained climbing plants, and soft daylight.

![AI-generated interior of a glazed gallery with laminated timber arches, climbing plants, planters and soft furniture against an existing brick wall]({{ '/assets/images/2026/sketch-and-model-to-material-preview/02-material-palette-render.jpg' | relative_url }})
*The palette image. AI-generated (Gemini).*

**2. Fitting the palette to the model.** The palette was then applied to the model photograph. The first attempt got the orientation and depth wrong. It turned the arches into a long conservatory running the length of the gap, and added more bays than the model has.

![AI render of the model showing the arches reinterpreted as a long glazed conservatory running along the gap]({{ '/assets/images/2026/sketch-and-model-to-material-preview/04-first-pass-render.jpg' | relative_url }})
*First attempt: wrong orientation. AI-generated (Gemini).*

The fix was to give the tool explicit spatial rules: do not change the physical structure of the model; rotate the arches 90 degrees to match the existing bays; keep five arches.

![AI render with the arches facing the viewer as on the model, dressed with timber, planting and glazing]({{ '/assets/images/2026/sketch-and-model-to-material-preview/05-arches-corrected.jpg' | relative_url }})
*After the spatial constraints: arches now read as on the model. AI-generated (Gemini).*

**3. Context and scale.** The last prompts added weathered, reddish-orange Victorian brickwork to the solid blocks at each end, representing the existing school building, and small scale figures walking through and past the gallery.

## Result

The final image turns the brown card and loose acrylic of the model into a credible material preview. It shows how pale timber, climbing planting and Victorian masonry might sit together, and it does this on the model's own geometry rather than on a structure the tool invented.

![Final AI render of the model with brick-textured end blocks, planted timber arches, glazing and scale figures]({{ '/assets/images/2026/sketch-and-model-to-material-preview/06-final-brick-and-figures.jpg' | relative_url }})
*Final render with brickwork and scale figures. AI-generated (Gemini).*

## Reflection

**What it added**

- **Speed.** Materials, glazing and planting were tested in a short session rather than hours of CAD modelling or Photoshop work.
- **Sketch to volume.** Seeing the sketch's ideas on the physical model made it easier to judge whether they work in three dimensions, not just in one drawn view.
- **Atmosphere early.** Moving from abstract card to Victorian brick and human figures gives a client or tutor a sense of the space at a stage when it would normally still be grey massing.
- **Control through constraints.** The output only became useful once geometric rules were fed back to the tool: keep the model as it is, match the bay orientation, keep five arches. Without them it drifted towards a structure of its own.

**What it got wrong**

- The first model render ignored the bay orientation and the number of arches entirely. Specific, measurable constraints were what corrected it; descriptive language alone did not.
- In the final image the brick texture has been applied to the roof planes as well as the walls. A Victorian roof would be slate or clay tile, so the render is wrong on a point a reader might take as a design decision.
- The scale figures inside the gallery are rendered as flat white silhouettes, unlike the figures outside. They read as model figures rather than people, which undercuts the "lived-in" aim.
- The renders are regenerated images, not overlays. Every pixel, including the background and the parts of the model the prompts did not mention, has been redrawn, so each output needs checking against the original photograph before it is trusted.
