---
title: AI Glossary
permalink: /glossary/
lead: Plain-English definitions of the AI terms that come up most often, written for architecture students.
---

This glossary started at our session on 5 March 2026, when we worked through the AI vocabulary that students said they hear all the time but were never quite sure about. The first section is the list we covered in that session. The second section adds further terms that tend to come up once you start using these tools on project work.

For a second plain-English reference, WellWired's [AI Jargon Buster](https://wellwired.ai/blog/ai-jargon-buster) covers 27 everyday terms. It is written for general readers rather than designers, but it is clear and UK-focused.

If a definition is unclear, or you think a term is missing, use the [contributor guide]({{ '/contribute/' | relative_url }}) to suggest a change.

## Terms from the session

### Machine Learning

A way of building software where, instead of a programmer writing every rule by hand, the computer works out the rules for itself by looking at lots of examples. Show a system thousands of photographs labelled "brick" or "render" and it gradually learns what features separate one from the other. Most of what people now call "AI" is machine learning of one kind or another.

### Training

The process of teaching a model by feeding it data and letting it adjust itself until its outputs improve. Training a large model takes huge amounts of data, computing power and money, and happens once (or occasionally) at the company that builds it. When you use ChatGPT, Claude or Gemini, you are not training it; you are using a model that has already been trained.

### Neural Network

The structure inside most modern AI models. It is loosely inspired by the brain: layers of simple connected units ("neurons") pass numbers to one another, and each connection has a strength that gets adjusted during training. No single connection means anything on its own. The knowledge sits in the pattern of millions or billions of connections, which is also why it is hard to explain exactly why a network gives a particular answer.

### Large Language Model (LLM)

A neural network trained on an enormous amount of text so that it can read and write language. At its core, an LLM predicts what text should come next, one small piece at a time. Done at a very large scale, that simple task produces something that can summarise a design brief, draft a planning statement or explain a building regulation. ChatGPT, Claude and Gemini are all built on LLMs. They are very good with language, but they do not "know" things the way a reference book does, and they can be confidently wrong (see Hallucination).

### Token

The unit an LLM actually reads and writes. A token is usually part of a word: in English, one token is roughly three-quarters of a word, so 100 tokens is about 75 words. Short common words are often a single token, while longer or unusual words ("fenestration") may be split into several. Tokens matter because usage limits, pricing and the context window are all measured in them.

### Context Window

The amount of text (measured in tokens) a model can hold in view at one time. This includes your prompt, any documents you upload, and the conversation so far. Think of it as the model's desk: everything on the desk can be used, but anything that falls off the edge is forgotten. If you paste a long brief and a long conversation follows, the model may lose track of details from the start. Context windows vary a great deal between models and are growing quickly.

### Prompt

Whatever you give an AI model to respond to. Usually this is a typed instruction or question, but it can also include images, sketches, PDFs or drawings. "Write a 300-word design statement for a community library on a brownfield site in Wolverhampton" is a prompt.

### Prompt Engineering

The skill of writing prompts that get useful results. In practice it means being specific about the task, giving the model context (who it is for, what stage the project is at), showing examples of what you want, saying what format you need, and stating what to avoid. Much like a good design brief, a vague prompt produces a vague answer. The term sounds technical, but most of it is clear writing.

### Hallucination

When an AI model produces something that sounds plausible but is false: a made-up reference, a building regulation clause that does not exist, an architect who never designed the building attributed to them, or a statistic with no source. It happens because the model generates likely-sounding text rather than looking facts up. Always check facts, figures, references and regulations against a reliable source before you use them in your work.

### RAG (Retrieval-Augmented Generation)

A technique that lets a model look things up before it answers. When you ask a question, the system first searches a set of trusted documents (for example, a practice's technical library, the Approved Documents or a project's specification) and passes the relevant passages to the model, which then writes its answer from them. It does not stop hallucination completely, but it reduces it, and it means the answer can point to its sources.

### Fine-Tuning

Taking a model that has already been trained and giving it extra training on a smaller, specialist set of examples so it gets better at one particular job or style. A practice could, in principle, fine-tune a model on its own past reports so the output matches its house style. Fine-tuning changes the model itself, whereas RAG leaves the model unchanged and supplies it with information at the moment you ask.

### Diffusion Model

The type of model behind most AI image generators, including Stable Diffusion. It learns by taking real images, gradually adding random noise until nothing is left but static, and learning how to reverse that process. To generate a new image, it starts from pure noise and removes it step by step, guided by your prompt, until a picture emerges. This is why the same prompt can give a different image each time, and why fine detail such as window mullions, stair geometry or text on signage often comes out wrong.

### Multimodal AI

AI that can work with more than one kind of input or output: text, images, audio, video, and sometimes 3D data. A multimodal model could look at a photograph of a site, read your written brief, and describe the constraints it sees, or take a hand sketch and turn it into a rendered image. Many of the mainstream assistants are now multimodal.

### AI Agent

An AI system that does not just answer a single question but works through a task in several steps, deciding what to do next and using tools along the way. Tools might include searching the web, reading files, running code, or operating other software. Where a chatbot gives you an answer, an agent might research precedents, gather the results into a document and save it for you. Agents can save a lot of time, but they also need checking, because a mistake early in a chain of steps carries through to the end.

## Further terms

### Algorithm

A step-by-step set of instructions that tells a computer how to get from an input to a result. Every piece of software runs on algorithms, AI or not. The difference with machine learning is that the detailed rules are learned from data rather than written out by a person, although the training process itself is still an algorithm.

### Artificial Intelligence (AI)

The broad field of making computers do tasks that would normally need human intelligence, such as recognising images, understanding language or making decisions. It is an umbrella term: machine learning, LLMs and diffusion models all sit underneath it.

### Generative AI

AI that creates new content (text, images, video, music, 3D models) rather than only sorting or analysing existing data. ChatGPT writing an essay and an image generator producing a concept render are both generative AI. Most of the current excitement, and most of the concern, is about this category.

### AGI (Artificial General Intelligence)

A hypothetical future AI that could handle any intellectual task a person can, rather than being good at a narrow range of things. It does not exist, and experts disagree sharply about whether, or when, it might. You will see the term often in news coverage and company announcements, so treat confident predictions about it with caution.

### Natural Language Processing (NLP)

The branch of AI concerned with understanding and producing human language: translation, speech recognition, summarising, answering questions. It is an older field than LLMs, which are now its most powerful tools. NLP is what lets you instruct software in ordinary sentences instead of menus and commands.

### Chatbot and Bot

A bot is any program that carries out automated tasks online. A chatbot is a bot built for conversation. Older chatbots followed fixed scripts, like the help window on a bank's website. Today's AI chatbots, such as ChatGPT, Claude and Gemini, run on LLMs, so they can respond to almost anything you type, with the strengths and weaknesses that come with that.

### Automation

Getting technology to carry out tasks without a person doing each step. Automation is not always AI: a Dynamo script that renumbers every door in a Revit model is automation following fixed rules, with no learning involved. AI-driven automation is used where the task needs judgement that is hard to write as rules, such as sorting survey photographs or drafting meeting minutes.

### Deep Learning

Machine learning that uses neural networks with many layers. The "deep" refers to the number of layers, not to any depth of understanding. Nearly all of today's headline AI tools use deep learning.

### Model

The trained system itself: the file of learned numbers that takes an input and produces an output. Products and apps are built around models. ChatGPT is a product; the GPT model inside it is what does the work. A single product may offer several models, usually trading speed against quality.

### Parameters

The adjustable numbers inside a model that are set during training, such as the connection strengths in a neural network. Large models have billions of them. More parameters usually means a more capable model, but also one that is slower and more expensive to run. You will sometimes see model names that include a parameter count, such as "70B" for 70 billion.

### Inference

The technical word for using a trained model to produce an output. Training is when the model learns; inference is every time you ask it something afterwards.

### Training Data

The material a model learned from. For LLMs this is mostly text gathered from the internet, books and other sources; for image generators it is huge collections of images with captions. What is in the training data shapes what a model can do well, what it gets wrong, and whose work it may have drawn on, which is the source of much of the copyright debate around generative AI.

### Bias

Systematic skew in what a model produces, usually inherited from its training data. Ask an image generator for "an architect" and look at who it shows you. Ask for "a beautiful house" and notice which styles and countries it favours. Bias is not always obvious, and it is worth asking whose buildings, cities and people are missing from what a tool produces.

### Knowledge Cutoff

The date after which a model has no information, because its training data stops there. A model may not know about recent regulation changes, new products or current events unless it is connected to web search or given the information in your prompt.

### Transformer

The neural network design that made modern LLMs possible, introduced by Google researchers in 2017. Its key idea, called "attention", lets the model weigh how every word in a passage relates to every other word, which is how it keeps track of meaning across long pieces of text. The "T" in GPT stands for transformer.

### Embedding

A way of turning words, images or documents into lists of numbers so that items with similar meanings end up close together. Embeddings are what let a system find a document about "thermal bridging at window reveals" when you searched for "cold spots around windows", even though the words differ. They are central to how RAG finds the right passages.

### System Prompt

Instructions given to a model behind the scenes, before your own prompt, that set how it should behave: its role, tone and rules. Companies use system prompts to shape their products, and many tools let you write your own (sometimes called custom instructions) so you do not have to repeat your requirements every time.

### Temperature

A setting that controls how predictable or varied a model's output is. Low temperature gives safer, more consistent answers; high temperature gives more varied and inventive ones, with more risk of nonsense. Most chat apps hide this setting, but you will meet it in more technical tools.

### Reasoning Model

A type of LLM that works through a problem in steps before giving its final answer, rather than replying straight away. Reasoning models are usually better at maths, logic, planning and multi-step problems, but they take longer and cost more to run. They can still be wrong, so the reasoning is not a guarantee.

### Agentic AI

The general term for AI systems that act as agents (see AI Agent): taking on a goal, planning the steps and carrying them out, often across several apps, with limited supervision. It is one of the most talked-about areas of AI and one of the least mature, so claims about what agentic systems can reliably do deserve scepticism. Giving software the power to act on your behalf also raises security questions that simple chat does not.

### Explainability

How far a person can understand why an AI system produced a particular output. Neural networks are notoriously hard to explain, even for the people who built them. This matters wherever decisions have consequences: if an AI tool flags a design as non-compliant, or a contractor's bid as high risk, someone needs to be able to see the reasoning and challenge it.

### Text-to-Image and Image-to-Image

Two common ways of using an image generator. Text-to-image creates a picture from a written prompt alone. Image-to-image starts from an existing picture (a sketch, a massing screenshot from Revit or SketchUp, a site photo) and transforms it according to your prompt. Image-to-image is usually far more useful for design work, because it keeps your composition and geometry.

### Seed

A number that sets the starting noise for an image generator. Using the same prompt, settings and seed will reproduce the same image; changing the seed gives a variation. Recording the seed is useful if you need to return to an image or show how you produced it.

### Negative Prompt

In some image tools, a separate instruction listing what you do not want, such as "blurry, distorted windows, people, text". It steers the output away from common problems.

### Inpainting and Outpainting

Editing tools in image generators. Inpainting regenerates only a selected part of an image (replacing a cladding material or adding landscaping) while leaving the rest alone. Outpainting extends an image beyond its original edges, for example widening a street view.

### ControlNet

An add-on for Stable Diffusion that makes the generated image follow a guide image closely, such as line work, edges, a depth map or a figure's pose. For architects this is significant, because it means an AI render can respect the actual geometry of your model rather than inventing its own.

### LoRA (Low-Rank Adaptation)

A small add-on file that adjusts an existing model towards a particular style or subject without retraining the whole thing. It is a lightweight form of fine-tuning, widely used with image generators, for example to keep a consistent rendering style across a set of images.

### Upscaling

Using AI to increase an image's resolution, adding plausible detail as it enlarges. Useful for presentation boards, but the added detail is invented, so check that it has not changed anything that matters.

### Open-Weight Model

A model whose trained parameters (weights) are published so that anyone can download and run it on their own hardware, adapt it or fine-tune it. Closed models, such as those behind most commercial chatbots, can only be used through the company's own app or service. Open-weight models give more control and privacy; closed models are often more capable and easier to use.

### Open Source

Software whose code is published so anyone can inspect, modify and share it. With AI the term is used loosely. Many models described as "open source" are really open-weight: the trained model is released, but the training data and full method are not. If openness matters to you, check exactly what has been released.

### Cloud Computing

Running software and storing data on someone else's computers, reached over the internet, rather than on your own machine. Almost every mainstream AI tool runs in the cloud, which is why it works on a modest laptop, and also why whatever you upload leaves your device (see Data Privacy). Autodesk Construction Cloud and similar platforms are the same idea applied to project data.

### Guardrails

Rules and filters built into AI tools to stop them producing harmful, illegal or inappropriate content. They are why a tool will sometimes refuse a request.

### Model Context Protocol (MCP)

An open standard, introduced by Anthropic in November 2024, for connecting AI models to other software and data sources, such as file storage, calendars or design tools. A useful comparison is USB-C: one standard plug instead of a different cable for every device. It is part of what allows AI agents to act inside the applications you already use, rather than only in a chat window. By the end of 2025 it had been handed to an open foundation, so no single company controls it.

### Computer Vision

The branch of AI concerned with understanding images and video: recognising objects, reading text, measuring and detecting changes. In the built environment it is used for things like identifying defects in survey photographs, classifying point clouds from laser scans and monitoring progress on site.

### Deepfake

AI-generated or AI-altered images, video or audio made to look like a real person or a real event. Relevant to architecture too: a convincing render of a building that does not exist, or a doctored site photo, can mislead clients, planners or the public.

### AI Slop

Low-quality AI-generated content produced in bulk and shared without much thought: generic text, odd images, recycled clichés. Architecture has its own version, from feeds full of glossy AI "concepts" with impossible structures to portfolios padded with renders that show no design thinking. The test is simple: could you explain and defend every decision in the image? If not, it is not design work yet.

### Data Privacy (What Happens to Your Uploads)

Before you upload drawings, client information or coursework to an AI tool, check its terms: whether your files are stored, whether they may be used to train future models, and who owns the outputs. Many tools offer settings to opt out of training. Do not upload anything confidential, or anything you do not have permission to share.

### AI Disclosure

Stating clearly where and how you used AI in a piece of work: which tool, for what, and what you changed afterwards. Check the University's current guidance and your module's assessment brief on acceptable use, and expect to explain your process. Every post on this site includes an AI disclosure for the same reason.
