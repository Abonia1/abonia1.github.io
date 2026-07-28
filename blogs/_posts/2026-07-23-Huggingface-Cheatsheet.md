---
layout: post
title: HuggingFace Cheatsheet

image: 
  path: /assets/img/blog/hf_hub_core.png
description: >
    A curated 5-page cheatsheet covering the core Hugging Face ecosystem, including the Hub, Transformers, Datasets, training, fine-tuning, inference, deployment, generative models, multimodal architectures, agents, and Hub tooling.
sitemap: false
---
  **Reading_time:** 5 min\
  **Tags:** [Hugging Face, Transformers, Machine Learning, Deep Learning, LLM, NLP, Model Training, Fine-Tuning, Inference, Model Deployment, Generative AI, Multimodal AI, AI Agents, MLOps, Open Source]
- Table of Contents
{:toc .large-only}

# 🤗 A 5-Page HuggingFace Cheatsheet
 Recently curated this **5-page Hugging Face Ecosystem Cheatsheet** 🤗

📥 **Download the cheatsheet:** [GitHub-Repository](https://github.com/Abonia1/HuggingFace-CheatSheet/)
---

## Why I Created This Cheatsheet

While working with pretrained models, datasets, fine-tuning workflows, inference systems, and deployment tools, I found that the Hugging Face ecosystem covers many different parts of the machine learning lifecycle.

There are libraries for specific tasks, platforms for sharing and versioning models and datasets, tools for training and fine-tuning, inference runtimes, deployment options, and frameworks for generative models and agents.

For someone learning the ecosystem, it can be useful to first have a high-level map of how these components relate to each other.

This is the reason I created this cheatsheet.

It is not intended to replace the official documentation or provide a complete reference to every library and API.

Instead, I tried to curate the core concepts into five pages that can be used as a visual reference.

---

## 📄 What the Cheatsheet Covers

### 1️⃣ Hugging Face Ecosystem & Hub Architecture

The first page introduces the main components of the Hugging Face ecosystem:

**Hub → Models → Datasets → Spaces → Organizations → Collections → Papers → Inference → Leaderboards**

It also covers model repository anatomy, common model artifacts, revisions, Dataset Cards, model discovery, filtering, licensing, hardware compatibility, and authentication.

![Hugging Face Ecosystem & Hub Architecture](/assets/img/blog/hf-slide1.PNG)

---

### 2️⃣ Transformers & Model Execution

The second page focuses on the execution path of pretrained transformer architectures.

The basic flow is:

**Input → Tokenizer / Processor → Model → Output**

It covers Auto Classes, task-specific model heads, tokenization, padding, truncation, sequence-length constraints, multimodal processors, Pipelines, direct model APIs, generation configuration, and chat templates.

![Transformers & Model Execution](/assets/img/blog/hf-slide2.PNG)

---

### 3️⃣ Datasets & Training Stack

The third page focuses on the data and training workflow.

It covers dataset loading, dataset splits, filtering, mapping, preprocessing, streaming, tokenization, batching, Data Collators, `Trainer`, `TrainingArguments`, `Accelerate`, PEFT, LoRA, QLoRA, evaluation, and Hub integration.

![Datasets & Training Stack](/assets/img/blog/hf-slide3.PNG)

---

### 4️⃣ Inference Stack & Deployment

The fourth page focuses on how model artifacts can be executed and served.

It covers local inference, `InferenceClient`, Text Generation Inference, continuous batching, streaming, tensor parallelism, Dedicated Endpoints, quantization, BitsAndBytes, AWQ, GPTQ, Optimum, hardware optimization, vLLM, llama.cpp, and Spaces.

![Inference Stack & Deployment](/assets/img/blog/hf-slide4.PNG)

---

### 5️⃣ Agents, Generative Models & Hub Tooling

The final page covers several higher-level components of the ecosystem.

It includes `smolagents`, Diffusers, TRL, post-training and alignment methods, multimodal architectures, Hub CLI workflows, and Python utilities such as `hf_hub_download` and `snapshot_download`.

![Agents, Generative Models & Hub Tooling](/assets/img/blog/hf-slide5.PNG)

---

## 🧭 The Structure

The five pages are organized around a simplified development lifecycle:

```text
Discover
    ↓
Load
    ↓
Prepare
    ↓
Train
    ↓
Fine-Tune
    ↓
Evaluate
    ↓
Optimize
    ↓
Serve
    ↓
Build
````

The purpose of this structure is to provide a starting point for understanding where different Hugging Face tools and services fit within a broader workflow.

---

## 🎯 Who Might Find It Useful?

I hope this cheatsheet can be useful for:

* Machine Learning Engineers.
* AI Engineers.
* LLM Engineers.
* Research Engineers.
* Applied Scientists.
* Data Scientists working with pretrained models.
* Students and practitioners learning the Hugging Face ecosystem.

It can be used as:

* A quick reference while working with Hugging Face tools.
* A learning aid for understanding the ecosystem.
* A teaching resource.
* A starting point for exploring the official documentation in more depth.

---

## 📥 Access the Cheatsheet

The complete cheatsheet is available here:

🔗 **Download:** [HD-Version](https://github.com/Abonia1/HuggingFace-CheatSheet/)

I hope this curated reference helps make the Hugging Face ecosystem a little easier to navigate and provides a useful starting point for further learning.

🤗

**Happy learning! 📖✨**

---
***Thanks for Reading!***

**[Website/Newletter](https://abonia1.github.io/)**
**[AIMagazine Substack](https://aboniasojasingarayar.substack.com)**

Connect with me on **[Linkedin](https://www.linkedin.com/in/aboniasojasingarayar/)**

Find me on **[Github](https://github.com/Abonia1)**

Visit my technical channel on **[Youtube](https://www.youtube.com/@AboniaSojasingarayar)**

Support: **[Buy me a Cofee/Chai](https://www.buymeacoffee.com/abonia)**