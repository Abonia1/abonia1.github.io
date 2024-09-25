---
layout: post
title: Multi-Modal Retrieval - Bridging Text and Images with BGE and CLIP
image: 
  path: /assets/img/blog/Multi-ModalRetriever.png
description: >
  In today’s data-rich world, being able to retrieve relevant information across different modalities (text, images, audio) has become increasingly important. This post will guide you through creating a multi-modal retrieval system that combines text embeddings from BGE (Bidirectional Generative Encoder) and image embeddings from CLIP (Contrastive Language-Instrumental Pre-training) to index and query Wikipedia articles.
sitemap: false
---

**[Link to the complete hands-on tutorial on Multi-Modal Retrieval - Bridging Text and Images with BGE and CLIP](https://youtu.be/9oogZrSTiM0?si=epr5kNKcrbzeZ52z)** 


  **Reading_time:** 5 min\
  **Tags:** [MultimodalRetrieval, AI, MachineLearning, NLP, ComputerVision, CLIP, BGE, ArtificialIntelligence, CrossModalSearch, TextEmbedding, ImageEmbedding, VectorSearch]
- Table of Contents
{:toc .large-only}


## Multi-Modal Retrieval: Bridging Text and Images with BGE and CLIP

### Building and Testing a Multi-Modal Retriever — Hands-On

In today’s data-rich world, being able to retrieve relevant information across different modalities (text, images, audio) has become increasingly important. This post will guide you through creating a multi-modal retrieval system that combines text embeddings from BGE (Bidirectional Generative Encoder) and image embeddings from CLIP (Contrastive Language-Instrumental Pre-training) to index and query Wikipedia articles.

<iframe width="900" height="500" src="https://www.youtube.com/embed/9oogZrSTiM0" frameborder="0" allowfullscreen></iframe>

In the rapidly evolving landscape of artificial intelligence and natural language processing, the ability to seamlessly integrate text and image information has become increasingly crucial. This article explores a cutting-edge approach to achieving this integration, leveraging state-of-the-art techniques to create a powerful demonstration of cross-modal retrieval capabilities.

## Understanding Multi-Modal Retrieval

Multi-modal retrieval allows us to search for information based on multiple types of input, such as text queries and image queries. It’s particularly useful for applications like visual search, content-based recommendation systems, and multimedia analysis.

Key aspects of multi-modal retrieval include:

* Indexing: Creating embeddings for both text and image data

* Querying: Processing user inputs and finding similar matches

* Ranking: Ordering results based on relevance

### Technical Overview

The proposed system utilizes several advanced techniques to enable efficient and accurate retrieval of both textual and visual content:

1. Text Embedding Index: 
 — Utilizes BAAI/bge-small-en-v1.5 for text representation
 — Employs Hugging Face (HF) embedding for query encoding

2. Image Embedding Index:
 — Implements CLIP embeddings from sentence transformers
 — Leverages CLIP embedding for image query encoding

3. Query Encoder:
 — Processes text queries using HF embedding
 — Processes image queries using CLIP embedding

4. Framework:
 — Built on top of LlamaIndex for efficient vector storage and retrieval

### Data Preparation

Before implementing the retrieval system, a crucial step involves preparing the necessary datasets:

- Download raw text and image files for Wikipedia articles
- These files serve as the foundation for building comprehensive indexes

### Building the Vector Store

With the data at hand, the next step is to construct the vector store:

1. Text Index Construction:
 — Apply BAAI/bge-small-en-v1.5 embeddings to text data
 — Create a vector store using these embeddings

2. Image Index Construction:
 — Generate CLIP embeddings for image data
 — Build a separate vector store for the image embeddings

### Query Processing and Retrieval

Once the vector store is populated, the system can handle various types of queries:

1. Text Queries:
 — Encode input text using HF embedding
 — Search the text index for relevant matches

2. Image Queries:
 — Extract features from input images using CLIP embedding
 — Search the image index for visually similar content

3. Cross-Modal Queries:
 — Combine text and image queries for simultaneous retrieval
 — Leverage the power of both indices to find relevant information

## Tutorial 

A user searches for “Bat man” using a combination of text and image queries. The system would:

1. Process the text query using HF embedding
2. Retrieve relevant Wikipedia articles from the text index
3. Simultaneously process the image query (e.g., a photo of Mars, Batman)
4. Find visually similar images from the image index
5. Return a combined result set that includes both textually and visually relevant information

This tutorial highlights the system’s ability to bridge the gap between linguistic and visual representations, providing users with a comprehensive understanding of complex topics through multimodal retrieval.

## Colab Notebook

**[Link to the complete Notebook](https://github.com/Abonia1/Multi-Modal-Retriever/blob/main/multi_modal_retrieval.ipynb)** 

<script src="https://gist.github.com/Abonia1/a0c555f6e53bc271fe305d29983af645.js"></script>

![](https://cdn-images-1.medium.com/max/2360/1*xkAvz-IDGh9MVxcx7MBkXA.png)

## Conclusion

By integrating cutting-edge text and image embedding techniques within a unified framework, this system offers a powerful tool for information retrieval across modalities. Its potential applications extend beyond simple demonstrations, potentially revolutionizing how we interact with and understand complex information in various domains such as education, research, and entertainment. As AI technology continues to advance, such systems will play an increasingly important role in facilitating human-computer interaction and knowledge acquisition.


Lets learn and grow together!


---
***Thanks for Reading!***

**[Website/Newletter](https://abonia1.github.io/)**
**[AIMagazine Substack](https://aboniasojasingarayar.substack.com)**

Connect with me on **[Linkedin](https://www.linkedin.com/in/aboniasojasingarayar/)**

Find me on **[Github](https://github.com/Abonia1)**

Visit my technical channel on **[Youtube](https://www.youtube.com/@AboniaSojasingarayar)**

Support: **[Buy me a Cofee/Chai](https://www.buymeacoffee.com/abonia)**