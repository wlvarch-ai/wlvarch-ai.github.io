---
title: "Workflow: rendering a 2D Revit plan with Gemini's Nano Banana"
date: 2026-04-23
author: "David Heesom"
summary: "Turn a 2D floor plan exported from Revit into a rendered top-down image with Gemini, then refine it with follow-up prompts, JSON and sketch mark-up."
tags: [workflow, image-generation, nano-banana, gemini, revit, json]
ai_disclosure: "All rendered images generated with Google Gemini (Nano Banana 2). Worlflow text drafted with support from AI tools from the author's notes, and reviewed and edited by the author."
---

This workflow was first demonstrated at our [23 April 2026 session]({{ '/sessions/' | relative_url }}). It takes a plain 2D plan from Revit and turns it into a rendered, presentation-style plan in Google Gemini, then refines it in stages.

## Good for

- Quick, atmospheric plan renders for early-stage presentations, crits and mood studies.
- Testing material and colour palettes across a layout before committing to them in the model.
- Learning how an AI tool reads a drawing, and where it gets it wrong.

## Not good for

- **Anything that has to be accurate.** The render is a picture of your plan, not a drawing of it. In our example the first render changed several things despite being told not to (compare images 1 and 2 below):
  - **The reception desk became a sofa.** The curved desk in the lobby was rendered as a cream curved lounger. The JSON step later confirmed the AI had read it as "Curved modular lounger".
  - **The door leaves disappeared.** Every door, including the double entrance doors, became an open gap.
  - **A window was added.** The east wall gained a second window beside the sofas that is not on the plan.
  - **Furniture moved.** The office chair shifted from below the desk to its side.
- **Technical or statutory drawings.** Never use the output as a planning, building regulations or construction drawing.
- **Exact repeatability.** The same prompt will not give the same image twice.
- **Long editing sessions.** After many changes in one chat, the tool starts to lose track and earlier fixes can come undone (see step 7).

Check every render against your original plan, element by element, before you show it to anyone.

## You will need

- Autodesk Revit or AutoCAD, to export the plan as an image (PNG or JPG).
- A Google account and access to [Gemini](https://gemini.google.com/). The free tier works but has daily limits on image generation.
- A clean plan: walls, doors, windows and furniture, with as little text, dimensioning and annotation as possible.

## Steps

### 1. Export a clean plan

Export the floor plan view as an image. Turn off dimensions, tags and text where you can; the cleaner the drawing, the less the AI has to guess.

![Plain 2D floor plan exported from Revit, showing an L-shaped building with a meeting room, an office and an open lobby]({{ '/assets/images/2026/cad-plan-to-render/01-revit-plan.jpg' | relative_url }})
*Image 1: the starting plan, exported from Revit.*

### 2. Write a structured first prompt

Upload the plan to Gemini with a prompt that uses the role, context, task and output structure from our [prompt engineering session]({{ '/sessions/' | relative_url }}). The context section matters: it tells the tool how to read Revit's drawing conventions.

```
<role>An experienced architectural illustrator with expertise in understanding architectural plans and creating digital realistic visualisations.</role>

<context>The attached image shows an architectural floor plan created by Autodesk Revit software. Walls are depicted as solid grey objects in the plan. Doors are depicted in the original as quarter-circle shapes. Windows are shown as multi-line objects aligned with a wall. Individual line shapes depict pieces of free-standing furniture.</context>

<task>Generate a photorealistic architectural rendering from the provided floor plan. Create a top-down view with some shallow perspective showing the complete layout with accurate room proportions and spatial relationships. Do not change any locations of walls, windows or doors. Do not change any location of furniture and do not add any additional items of furniture to the image. Apply a modern, contemporary aesthetic throughout, ensuring consistent material choices, colour palette and lighting treatment that match the selected design style. Include realistic textures for all surfaces such as flooring, walls and furnishings. Do not change the location or style of furniture and fixtures. Any materials used should be scaled correctly for each room. Ensure natural and artificial lighting creates depth and atmosphere while highlighting architectural features.</task>

<output>High-quality renders suitable for architectural presentation. If there is any text in the floor plan, please remove it. The final image should be on a white background.</output>
```

![Rendered top-down plan with concrete floors, a walnut meeting table, cove lighting and a cream curved lounger in the lobby]({{ '/assets/images/2026/cad-plan-to-render/02-first-render.jpg' | relative_url }})
*Image 2: the first render. Convincing at a glance, but compare it with image 1: the reception desk is now a lounger, the doors have gone and the east wall has an extra window.*

### 3. Add entourage in a follow-up prompt

Make one change at a time. To add planting:

```
Add in a small amount of biophilic entourage to rooms. This should be small scale and proportionately sized for the buildings. Any additional elements added should match the perspective of the image you have just created.
```

![The same render with small potted plants added to the meeting table, office corner, lobby window and entrance]({{ '/assets/images/2026/cad-plan-to-render/03-biophilic-entourage.jpg' | relative_url }})
*Image 3: small-scale planting added, matching the existing view.*

**The last sentence matters.** Without the instruction to match the perspective, the tool treated the request as a fresh render. It changed the flooring and furniture, swapped the lounger back to a timber desk, and placed a plant pot on top of a wall.

![A different render of the same plan with timber and carpet floors, large plants, and a plant pot sitting on top of the wall by the entrance]({{ '/assets/images/2026/cad-plan-to-render/04-no-perspective-instruction.jpg' | relative_url }})
*Image 4: the same request without the perspective instruction. Note the plant pot on the wall at the bottom left of the lobby.*

### 4. Extract the image as JSON

Ask the tool to describe what it has produced as structured data:

```
Extract all the info from this image and convert it to structured JSON.
```

In our example it returned this:

```json
{
  "project_metadata": {
    "source_file": "PhotoshopProject.jpg",
    "software_origin": "Autodesk Revit",
    "style_aesthetic": "Modern Contemporary",
    "visualization_type": "Top-down rendered floor plan",
    "background": "White"
  },
  "architectural_elements": {
    "walls": {
      "type": "Solid grey / White rendered",
      "material": "Plaster finish",
      "thickness": "Standard interior/exterior"
    },
    "apertures": {
      "doors": [
        { "type": "Single swing", "location": "North-west room entry" },
        { "type": "Single swing", "location": "South-west room entry" },
        { "type": "Double swing/French", "location": "South main entrance" }
      ],
      "windows": [
        { "count": 2, "location": "South wall" },
        { "count": 1, "location": "East wall" },
        { "count": 1, "location": "North wall" }
      ]
    }
  },
  "room_analysis": {
    "dining_meeting_room_northwest": {
      "flooring": "Polished concrete / Grey stone",
      "lighting": "Warm LED perimeter cove lighting",
      "furniture": [
        { "item": "Rectangular dining/conference table", "material": "Dark wood / Walnut" },
        { "item": "Executive chairs", "count": 8, "material": "Dark upholstery" },
        { "item": "Tabletop biophilic element", "description": "Small succulent/potted arrangement" }
      ]
    },
    "private_office_southwest": {
      "flooring": "Polished concrete / Grey stone",
      "lighting": "Warm LED perimeter cove lighting",
      "furniture": [
        { "item": "L-shaped / Ergonomic desk", "color": "Light grey/white" },
        { "item": "Task chair", "type": "High-back executive", "color": "Black" },
        { "item": "Floor plant", "description": "Small potted biophilic accent" }
      ]
    },
    "open_plan_living_lobby_east": {
      "flooring": "Polished concrete / Grey stone",
      "lighting": "Warm LED perimeter cove lighting (North/East walls)",
      "furniture": [
        { "item": "Symmetrical sofas", "count": 2, "color": "Grey velvet/fabric" },
        { "item": "Coffee table", "material": "Glass / Transparent" },
        { "item": "Curved modular lounger", "color": "Cream/Off-white boucle" },
        { "item": "Accent side table", "material": "Stone/Marble" }
      ],
      "biophilic_entourage": [
        { "item": "Copper floor planter", "location": "South entrance nook" },
        { "item": "Window-sill planter", "location": "East wall" },
        { "item": "Tabletop plant", "location": "Side table" }
      ]
    }
  }
}
```

Read it critically. It is the tool's own account of the image, and it is not always consistent with it. It lists door types that no longer appear in the render, and one east window where the render shows two. It also gives away the misreading from step 2: the reception desk is listed as a "Curved modular lounger".

### 5. Edit the JSON and send it back

Change only the entries you want to alter, then paste the whole JSON back with an instruction. Here the lounger was changed back to what the plan intended:

```
Modify the image based on the following JSON data
[paste the full JSON, with your edits]
```

The only line edited in our example was:

```json
{ "item": "Curved Reception Desk", "color": "Glass / Transparent" }
```

![The render with the cream lounger replaced by a curved glass reception desk with a chair behind it]({{ '/assets/images/2026/cad-plan-to-render/05-json-glass-reception-desk.jpg' | relative_url }})
*Image 5: the lounger replaced with a curved glass reception desk, with the rest of the image unchanged.*

Labelled data gives you precise control: you change one element by name rather than describing it in a sentence and hoping the tool finds the right one.

### 6. Mark up the image directly

In Gemini you can click a generated image and sketch or write on it to show where a change should go. Here a rough outline and the word "Rug" were drawn in the lobby.

![The render with a red hand-drawn outline in the lobby and the word Rug written beside it]({{ '/assets/images/2026/cad-plan-to-render/06-markup-rug.jpg' | relative_url }})
*Image 6: sketch mark-up added in Gemini.*

![The render with a large patterned rug placed in the centre of the lobby]({{ '/assets/images/2026/cad-plan-to-render/07-markup-result.jpg' | relative_url }})
*Image 7: the rug added where it was marked.*

Note that the mark-up was made on the earlier version with the cream lounger, so the glass desk from step 5 does not appear in image 7. Changes only carry forward from the image you are editing, so keep track of which version you are working on.

### 7. Restart when the chat gets confused

This is trial and error, and long chats drift. As the conversation grows, the tool's [context window]({{ '/glossary/' | relative_url }}) fills with earlier versions and instructions, and it starts mixing them up. When that happens, download the last good image, open a new chat and use that image as your new starting point.

### 8. Check and disclose

Before using any render, compare it with your plan: walls, openings, doors, windows, furniture positions and room uses. Then state in your work which tool you used and what you changed. See [AI Disclosure]({{ '/glossary/' | relative_url }}) in the glossary.

## Example

Images 1 to 7 above are the full example, from a basic Revit plan to a furnished, lit plan render in five prompts and one mark-up. The most useful lesson came from the failures: the first prompt explicitly said not to change furniture or openings, and the tool changed both anyway. A good prompt gets you most of the way, but checking the output is not optional.

## Last tested

April 2026, in the Gemini app using Nano Banana 2.
