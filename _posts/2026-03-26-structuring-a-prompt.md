---
title: "Structuring a prompt: role, context, task, output, constraints"
date: 2026-03-26
author: "David Heesom"
summary: "We looked at prompt engineering in practice, using labelled sections to turn a vague request into a clear brief."
tags: [prompt-engineering, prompts, llm, bim]
open_question: "How much structure is enough? At what point does a longer prompt stop improving the answer?"
ai_disclosure: "Post drafted with support from AI tools from the author's session notes, and reviewed and edited by the author."
---

## Discussed

Following on from our [glossary session]({{ '/glossary/' | relative_url }}), we turned to prompt engineering: how the way you ask affects what you get back. Most weak AI output starts with a weak prompt. A one-line request leaves the tool to guess who you are, what you need and what a good answer looks like.

We worked with a simple structure that splits a prompt into five labelled sections:

- **Role**: who the AI should act as, or whose perspective it should take.
- **Context**: the background it needs to pitch the answer correctly.
- **Task**: what you actually want done.
- **Output**: the format you want the result in.
- **Constraints**: limits and rules the answer must respect.

Each section goes inside a pair of tags, such as `<Role>` and `</Role>`. These are XML-style tags. They work as signposts, making it clear to the model where one part of the instruction ends and the next begins, so it is less likely to mix up your background information with your actual request. We also touched on JSON, another structured format that uses labelled fields to do a similar job.

Writing a prompt this way works a lot like writing a good design brief. It makes you decide what you want before you ask for it.

## Demonstrated

We built an example around a first-year research task:

```
<Role>You are an undergraduate student studying architecture at the University of Wolverhampton in the UK.</Role>

<Context>You are currently studying a module on Digital Design in the first year of the course and are looking to understand more around the topic of BIM.</Context>

<Task>Produce a background of the history of BIM and in particular how it is used by Architects and Architectural Technologists. Only use reliable industry or academic references as part of your research.</Task>

<Output>Based on the research, produce a bullet point list in a Microsoft Word document and include references to the content you use.</Output>

<Constraints>Only use references and information from the last 15 years.</Constraints>
```

Compare that with simply typing "tell me about BIM". The structured version tells the tool the level to pitch at, the professional focus, the quality of sources expected, the format and the time frame.

Even with a good prompt, check every reference the tool gives you. AI tools can produce convincing citations that do not exist (see [hallucination]({{ '/glossary/' | relative_url }})).

## Links

- [Prompt engineering overview, Anthropic](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview): practical guidance on writing clear prompts, including the use of tags to separate parts of a prompt.
- [AI Glossary]({{ '/glossary/' | relative_url }}): see Prompt, Prompt Engineering, System Prompt and Hallucination.

## Next time

Try the five-part structure on a piece of your own module work and bring the prompt, and the result, to compare.
