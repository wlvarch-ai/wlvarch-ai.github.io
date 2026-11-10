---
title: "From 3D print to historical context"
date: 2026-04-01
author: "David Heesom (AI) and Samantha Elliott (Model)"
summary: "Using a single-colour 3D print on a hand-drawn site sketch as the base for staged image prompts that test Victorian materials, a matching annex and period street life."
tags: [showcase, concept design, 3D printing, physical model, image generation, heritage]
ai_disclosure: "The 3D print and the site sketch are the author's own. The three renders were produced with Google Gemini image generation from a photograph of the print and text prompts. No CAD, texturing or Photoshop work was done on the outputs."
---

This entry tests whether image generation can add material and historical character to a physical study model without throwing away its geometry. The base is a single-colour 3D print placed on a hand-drawn site sketch, photographed on a studio desk.

## Starting point

The work began on the desk, not in a rendering package.

- **The print.** A monochrome green PLA print of the building and its annex. It fixes the massing, roof pitches, the proportions of the tower and the window reveals.
- **The sketch.** A hand-annotated tracing-paper site sketch under the print, marking the public entrance, seating, pedestrian movement and a sustainable drainage (SuDS) zone. It fixes orientation, access and context.

At this stage a detailed BIM model or a fully textured render would be premature. The photograph of the print on the sketch was used instead as the visual and spatial constraint for image-to-image generation.

![Green 3D-printed model of a Victorian school with a pyramidal-roofed tower, sitting on a tracing-paper site sketch annotated with entrance, seating and SuDS]({{ '/assets/images/2026/3d-print-to-historic-context/01-3d-print-on-site-sketch.jpg' | relative_url }})
*The starting point: PLA print on the annotated site sketch.*

## Method

The result was built up in stages rather than from one long prompt. Each stage kept the previous output and added one layer.

**1. Materials and vernacular.** The first prompt asked for no change to roof pitches, the tower silhouette or wall alignments, and set out a period palette for a Victorian Gothic Revival school:

- red/orange Victorian facing brick in English bond
- dressed sandstone quoins, mullions, window heads and plinth
- weathered Welsh slate with lead flashings and some moss
- dark-framed timber windows

![AI render of the main building in red brick with sandstone dressings, slate roofs and Gothic windows; the annex behind is still green plastic]({{ '/assets/images/2026/3d-print-to-historic-context/02-materials-main-block.jpg' | relative_url }})
*Stage 1: materials applied to the main block only. AI-generated (Gemini).*

**2. Matching the annex.** The second prompt kept the main block as it was and applied the same brick and slate to the annex in the background, so the whole group reads as one school.

![AI render with the annex in the background now matching the main building's brick and slate]({{ '/assets/images/2026/3d-print-to-historic-context/03-materials-annex.jpg' | relative_url }})
*Stage 2: annex brought into the same palette. AI-generated (Gemini).*

**3. Street, scale and period.** The final prompt added a cobbled ground plane, miniature figures in Victorian dress, and horse-drawn vehicles along the street edge.

## Result

The final image reads as a period scene: the school in brick and slate, a cobbled street, figures at the entrance and carriages at the kerb. The figures give an immediate sense of scale, and the main volumes of the print (the tower, the gabled ranges and the annex) are still recognisable.

![Final AI render with cobbled paving, grass, figures in Victorian dress and horse-drawn vehicles around the school]({{ '/assets/images/2026/3d-print-to-historic-context/04-final-context-and-entourage.jpg' | relative_url }})
*Stage 3: street, figures and vehicles. AI-generated (Gemini).*

## Reflection

**What it added**

- **The print as a constraint.** Starting from a photographed physical model kept the overall massing far closer to the design than a text prompt alone would. The model did the job a prompt cannot: it fixed the volumes.
- **Speed.** Material and atmosphere studies that would normally need texturing, lighting and entourage work were produced within a single session, at a stage where that effort would not otherwise be justified.
- **A case for physical models.** The physical model was not replaced by the digital workflow; it was what made the digital output disciplined.

**What it got wrong**

- **The geometry was not fully held.** Despite the instruction not to alter the model, the tool added chimneys to both buildings, an entrance door at the base of the tower and rainwater pipes, none of which are on the print. The plain rectangular window reveals on the print became pointed Gothic windows with tracery. These may be good design moves, but they are the tool's, not the author's, and need to be labelled as such.
- **The prompt was only partly followed.** The brickwork in the renders does not clearly show English bond, which was asked for. It needs checking at full resolution before it is described as such.
- **The site design was paved over.** In the final image the cobbles and lawn sit over the sketch, hiding the seating, pedestrian routes and SuDS zone the drawing set out. The scene shows the building's past, not the site proposal.
- **The figures are not what was described.** The brief asked for a headmaster, teachers and pupils. The figures generated are all adults, and the vehicles are a carriage and carts rather than delivery barrows.
- **The background was redrawn too.** The people at the desks behind have been regenerated along with everything else. Check that anyone recognisable in the original photograph is happy to appear before it is published.
