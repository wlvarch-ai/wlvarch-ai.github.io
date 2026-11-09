---
title: "RAG in practice: grounding AI in your own sources with NotebookLM"
date: 2026-04-16
author: "David Heesom and Nigel Moore"
summary: "We unpacked retrieval-augmented generation (RAG), why it reduces hallucination, and how NotebookLM puts it to work on your own module material."
tags: [rag, hallucination, notebooklm, study-tools]
open_question: "If a tool only answers from the sources we give it, how do we judge whether our sources are good enough?"
ai_disclosure: "Post drafted with support from AI tools from the author's session notes, and reviewed and edited by the author."
---

* July Update: in July 2026 Google renamed NotebookLM to Gemini Notebook. It is the same product, and existing notebooks and links still work. This post uses the name it had at the time of the session.*

## Discussed

This session picked up a term from our [glossary]({{ '/glossary/' | relative_url }}): RAG, or retrieval-augmented generation. It is one of the main ways AI tools try to deal with [hallucination]({{ '/glossary/' | relative_url }}), where a model produces confident answers that are simply wrong.

A standard chat tool answers from patterns it learned during training. It is not looking anything up, which is why it can invent references or regulations. A RAG system adds a step before the answer:

- **Retrieval**: the system searches a set of sources (your sources, in this case) for the passages most relevant to your question.
- **Augmentation**: those passages are added to the prompt, so the model has the actual material in front of it.
- **Generation**: the model writes its answer from that material, and can point to where each part came from.

The model still uses everything it learned in training to understand your question and write fluently. What changes is where the facts come from. Answers grounded in your sources are more reliable and easier to check, but not guaranteed. **Any LLM-based system can still hallucinate**, so check anything that matters against the source itself.

Nigel introduced NotebookLM from Google, built on Google's Gemini models, as one of the most usable RAG tools available, and one that academics use as well as students. You create a notebook, add your sources, and the tool answers questions from those sources, with citations you can click to see the exact passage it used.

NotebookLM is free to use, with daily limits, and paid tiers raise them. It accepts a range of source types, including PDFs, Google Docs and Slides, web pages, pasted text and YouTube videos (it works from the video's transcript). Beyond chat, its Studio panel can turn your sources into:

- podcast-style Audio Overviews
- video overviews
- mind maps
- infographics
- slide decks
- flashcards
- quizzes
- reports and study guides

Before uploading anything, think about what it is. Module materials and your own notes are fine for personal study, but do not upload confidential project information, other people's unpublished work or personal data.

## Demonstrated

David and Nigel each showed a notebook they have built for one of their modules, and how they use it to help students navigate module content:

- [Module notebook example 1](https://notebooklm.google.com/notebook/b58b6828-3907-46f6-aa79-c23c3460c6b7)
- [Module notebook example 2](https://notebooklm.google.com/notebook/b2e5b495-ff29-4a07-b20c-e491e80a5daa)

You will need to be signed in to a Google account to open them.

## Links

- [NotebookLM (now Gemini Notebook)](https://notebooklm.google.com/): free to start with a Google account.
- [AI Glossary]({{ '/glossary/' | relative_url }}): see RAG, Hallucination, Embedding and Multimodal AI.

## Next time

Build a notebook for one of your current modules from the lecture slides, readings and brief, then bring one output (a quiz, a mind map or an audio overview) and tell us what it got right and wrong.
