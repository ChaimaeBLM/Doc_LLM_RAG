Introduction
============

Welcome to the documentation for the RAG (Retrieval-Augmented Generation) application. 
This application leverages LangChain, Streamlit, Mistral, and Llama3 through Ollama to provide 
an interactive platform for testing and exploring language models and retrieval-augmented generation workflows.

.. image:: source\images\schema.png
   :alt: Example image showing the application flow
   :align: center


What exactly is RAG?
---------------------
RAG, or Retrieval Augmented Generation, is a technique that enhances LLMs by integrating additional data sources. A typical RAG application involves:

* **Indexing **- a pipeline for ingesting data from a source and indexing it, which usually consists of Loading, Splitting and Storing the data in ChromaDb.

* **Retrieval and generation** - At runtime, RAG processes the user's query, fetches relevant data from the index stored in ChromaDb, and the LLM generates a response based on this enriched context.

Key Technologies Used 
----------------------

Mistral & llama3 via Ollama
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Ollama is a free and open-source application that allows you to run various large language models,
including Llama 3, on your own computer, even with limited resources. Ollama takes advantage of the performance gains of llama.cpp,
an open source library designed to allow you to run LLMs locally with relatively low hardware requirements. It also includes a sort of package manager,
allowing you to download and use LLMs quickly and effectively with just a single command.

*Llama 3* comes in two sizes: 8 billion and 70 billion parameters. This kind of model is trained on a massive amount of text data and can be used for a variety 
of tasks, including generating text, translating languages, writing different kinds of creative content, and answering your questions in an informative way. 
Meta touts Llama 3 as one of the best open models available, but it is still under development.

.. image:: source\images\https___dev-to-uploads.s3.amazonaws.com_uploads_articles_ax9r9z2w2zghv81grbh7.png
   :alt: Mistral vs llama3
   :align: center



🦜️🔗 LangChain
^^^^^^^^^^^^^^^^
LangChain is a framework for developing applications powered by large language models (LLMs).

For these applications, LangChain simplifies the entire application lifecycle:

* **Open-source libraries:** Build your applications using LangChain's open-source building blocks, components, and third-party integrations. Use LangGraph to build stateful agents with first-class streaming and human-in-the-loop support.
Productionization: Inspect, monitor, and evaluate your apps with LangSmith so that you can constantly optimize and deploy with confidence.

* **Deployment:** Turn your LangGraph applications into production-ready APIs and Assistants with LangGraph Cloud.
Open-source libraries

* **langchain-core:** Base abstractions and LangChain Expression Language.

* **langchain-community:** Third party integrations.
Some integrations have been further split into partner packages that only rely on langchain-core. Examples include langchain_openai and langchain_anthropic.

* **langchain:** Chains, agents, and retrieval strategies that make up an application's cognitive architecture.

* **LangGraph:** A library for building robust and stateful multi-actor applications with LLMs by modeling steps as edges and nodes in a graph. Integrates smoothly with LangChain, but can be used without it. To learn more about LangGraph, check out our first LangChain Academy course, Introduction to LangGraph, available here.

*Productionization:

* **LangSmith:** A developer platform that lets you debug, test, evaluate, and monitor chains built on any LLM framework and seamlessly integrates with LangChain.

Streamlit
^^^^^^^^^^
Streamlit lets you transform Python scripts into interactive web apps in minutes, instead of weeks. Build dashboards, generate reports, or create chat apps. Once you’ve created an app, you can use our Community Cloud platform to deploy, manage, and share your app.

Why choose Streamlit?

* **Simple and Pythonic:** Write beautiful, easy-to-read code.

* **Fast, interactive prototyping:** Let others interact with your data and provide feedback quickly.

* **Live editing:** See your app update instantly as you edit your script.

* **Open-source and free:** Join a vibrant community and contribute to Streamlit's future.