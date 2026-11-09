---
title: "From CAD plan to render: prompting Gemini's Nano Banana"
date: 2026-04-23
author: "David"
summary: "In our last session of the year we turned a 2D Revit plan into a rendered image with Nano Banana, and used JSON to see how the AI had read the drawing."
tags: [image-generation, nano-banana, gemini, revit, json, workflow]
open_question: "When an AI render looks right, how do we check that it still matches the drawing it came from?"
ai_disclosure: "Post drafted with Claude (Anthropic) from the author's session notes, and reviewed and edited by the author."
---

## Discussed

For the last session of the academic year we moved from text to images. The question was a practical one: can you take a 2D floor plan exported from AutoCAD or Revit, describe the materials you want, and have an AI tool turn it into a rendered image?

We started with how AI image generators work. Many are built on [diffusion models]({{ '/glossary/' | relative_url }}), a type of machine learning that starts from random static (noise) and cleans and structures it step by step until a clear picture emerges. Midjourney and Stable Diffusion are well-known examples.

The tool we used was Google's Nano Banana, the image model built into Gemini, which has become very prominent. Google has not published full details of how it works. It is part of a newer group of image generators, ChatGPT's image tool among them, that are built into multimodal language models rather than standing alone, and that are widely reported to work differently from classic diffusion, generating the image in planned steps much as an LLM generates text. This is a large part of why they are so good at following detailed instructions and at editing an existing image rather than starting again.

## Demonstrated

We worked through an example using a basic Revit plan exported as an image and brought into Nano Banana, prompting it with descriptions of the materials we wanted.

We then went a step further. Before rendering, we asked the AI to describe the plan back to us as structured data in JSON, following the approach in [this video](https://youtu.be/cj3h3Fb10QY). The result shows exactly how the tool has read each element of the drawing. Here is a short extract:

```json
{
  "project_metadata": {
    "source_tool": "Autodesk Revit",
    "view_type": "2D Floor Plan",
    "unit_system": "Metric (Estimated)",
    "room_count": 3
  },
  "architectural_elements": {
    "walls": {
      "type": "Solid Fill",
      "color": "#808080",
      "description": "Continuous exterior and interior partition walls defining an L-shaped footprint."
    },
    "openings": [
      {
        "type": "Double Door",
        "location": "Bottom/Main Entrance",
        "swing": "Inward, double-leaf",
        "representation": "Two quarter-circle arcs"
      },
      {
        "type": "Single Door",
        "location": "Internal - Top Room",
        "swing": "Inward/Right",
        "representation": "Single quarter-circle arc"
      }
    ]
  }
}
```

This does two useful things. First, it gives you more control: once each element has a label, you can assign materials to walls, doors or rooms individually rather than hoping a general prompt lands in the right place. Second, it shows you what the AI has misread before you render anything. Notice the units are marked "Estimated". The JSON is the AI's interpretation of the drawing, not data taken from the Revit model, so check it against your plan.

This connects back to our [prompt engineering session]({{ '/sessions/' | relative_url }}): structure in, better control out.

You can find the workflow we used, step by step and with its limitations, in the [Workflows]({{ '/workflows/' | relative_url }}) section of the site.

## Links

- [Video: extracting drawing information into JSON](https://youtu.be/cj3h3Fb10QY): the approach we followed for the JSON step.
- [Gemini](https://gemini.google.com/): where Nano Banana is available.
- [AI Glossary]({{ '/glossary/' | relative_url }}): see Diffusion Model, Image-to-Image, Multimodal AI and Inpainting.

## Next time

This was the last session of 2025–26. Over the summer, try the workflow on a plan of your own and bring the results, good and bad, when the club returns.
