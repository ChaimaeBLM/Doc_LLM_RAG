Installation
=============

Prerequisites
-------------
* Python 3.8 +
* Virtual Environment

______________________

Steps to Install Dependencies
-----------------------------

1. Clone the github repository:

.. code-block:: python

    git clone https://github.com/ChaimaeBLM/Doc_LLM_RAG
    cd Doc_LLM_RAG

2. Set up a virtual environment:

.. code-block:: python

    python3 -m venv venv
    source venv/bin/activate
    # with anaconda
    conda create -n env_name python
    conda activate env_name

3. Download Ollama and run llama3 then Mistral

.. code-block:: python

    Ollama run llama3
    Ollama run Mistral

4. Installing Dependencies

.. code-block:: python

    # Document loading, retrieval methods and text splitting
    pip install -qU langchain langchain-community

    # Local vector store via Chroma
    Pip instal -qU langchain_chroma

    # Local inference and embeddings via Ollama
    pip install -qU langchain_Ollama

    # Web Loader
    pip install -qU beautifulsoup4




