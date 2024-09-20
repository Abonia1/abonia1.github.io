---
layout: post
title: Running Ollama in Google Colab (Free Tier)
image: 
  path: /assets/img/blog/ollama-in-colab.png
description: >
    Ollama empowers you to leverage powerful large language models (LLMs) like Llama2,Llama3,Phi3 etc. without needing a powerful local machine. Google Colab’s free tier provides a cloud environment perfectly suited for running these resource-intensive models. This tutorial details setting up and running Ollama on the free version of Google Colab, allowing you to explore the capabilities of LLMs without significant upfront costs.
sitemap: false
---

**[Link to the complete hands-on tutorial on Running Ollama in Google Colab (Free Tier)](https://youtu.be/UIZ5kdjYNMA)** 


  **Reading_time:** 5 min\
  **Tags:** [Ollama, colab, FreeTier, LLM, GenAI]
- Table of Contents
{:toc .large-only}

### A Step-by-Step Tutorial

Ollama empowers you to leverage powerful large language models (LLMs) like Llama2,Llama3,Phi3 etc. without needing a powerful local machine. Google Colab’s free tier provides a cloud environment perfectly suited for running these resource-intensive models. This tutorial details setting up and running Ollama on the free version of Google Colab, allowing you to explore the capabilities of LLMs without significant upfront costs.

<iframe width="900" height="500" src="https://www.youtube.com/embed/UIZ5kdjYNMA" frameborder="0" allowfullscreen></iframe>


You will learn:

* Why run Ollama in, Google Colab

* How to run Ollama in colab

Google Colab provides an excellent environment for running machine learning models and tools like Ollama. While Colab offers a generous free tier, we need to take some extra steps to ensure we can run Ollama effectively. Let’s go through this process step-by-step.

## Setting Up the Environment

First, we need to set up our Colab notebook to support command-line operations:

    !pip install colab-xterm
    %load_ext colabxterm

This code installs the `colab-xterm` library and enables the Colab XTerm extension, which allows us to run shell commands directly in our notebook .

## Installing and serving Ollama

To get started with Ollama, we’ll need to install it using the official installation script. Here’s how to do it:

### Launching Xterm

Now, let’s launch the xterm terminal within our Colab cell:

    %xterm

This command opens a full-screen terminal window within your Colab notebook.

### Installing Ollama

Once the xterm is open, we can proceed with the installation of Ollama. Run the following commands:

    curl https://ollama.ai/install.sh | sh

This command downloads the installation script from the Ollama website and executes it. The script will handle the installation process automatically, including downloading and installing necessary dependencies.

### Starting the Ollama Server

Once Ollama is installed, we can start the server using the following command:

    ollama serve &

The `&` at the end runs the command in the background, allowing you to continue using your terminal.

### Pulling AI Models

Now that the Ollama server is running, we can pull AI models to use with our server. Let’s pull the Mistral model as an example:

    ollama pull mistral

This command downloads the Mistral model and makes it available for use with your Ollama server.

### Verifying the Installation

Let’s verify that Ollama has been installed correctly:

    !ollama - version

This should display the version number of Ollama if the installation was successful.

## Running Ollama Commands

Now that we have Ollama installed, we can start using it. Here are a few basic commands to get you started:

    !ollama pull llama
    !ollama generate "Hello, world!"

The first command pulls the “llama” model, and the second generates text using that model.

### Sample Colab Notebook

<script src="https://gist.github.com/Abonia1/48ea45c147d15621b3f4dcc6a6ca2a2f.js"></script>


## Key Points to Consider

- While Ollama runs in Colab, it may not be as fast as running locally due to network latency and resource limitations of the free tier.
- Be mindful of your usage limits, especially if you plan to run multiple models or generate large amounts of text.
- Some advanced features of Ollama might not work perfectly in the Colab environment due to its virtual machine nature.

## Best Practices

1. Use smaller models: Choose lighter models like “llama” or “llama2” for better performance in Colab.
2. Generate text incrementally: If you need longer outputs, consider generating text in chunks rather than all at once.
3. Save your work: Remember to save your notebook frequently, as Colab sessions can sometimes terminate unexpectedly.
4. Clean up: After your session ends, you might want to remove Ollama to free up space:

    !rm -rf /usr/local/bin/ollama

By following these steps and best practices, you can effectively run Ollama in Google Colab using the free tier. This setup provides a convenient way to experiment with language models without needing to manage a local server or worry about hardware requirements.

---
***Thanks for Reading!***

**[Website/Newletter](https://abonia1.github.io/)**
**[AIMagazine Substack](https://aboniasojasingarayar.substack.com)**

Connect with me on **[Linkedin](https://www.linkedin.com/in/aboniasojasingarayar/)**

Find me on **[Github](https://github.com/Abonia1)**

Visit my technical channel on **[Youtube](https://www.youtube.com/@AboniaSojasingarayar)**

Support: **[Buy me a Cofee/Chai](https://www.buymeacoffee.com/abonia)**