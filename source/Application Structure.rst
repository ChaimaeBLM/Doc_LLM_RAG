Application Structure
======================
The app is organized into the following key components:

1. LLM Setup
------------
**Ollama LLMs:**
Two options are provided: Llama3 and Mistral.
The user selects the model via a dropdown menu.
The selected model is instantiated with Ollama from the langchain_community.llms module.

.. highlight:: python

    llm_options = {
    "Llama3": Ollama(model="llama3", base_url="http://127.0.0.1:11434"),
    "Mistral": Ollama(model="mistral", base_url="http://127.0.0.1:11434"),  # Replace with actual Mistral API if available
        }


2. Embedding and Vector Store
------------------------------
**Embedding Model:** OllamaEmbeddings generates vector embeddings for storing and retrieving document chunks.

.. highlight:: python

    embed_model = OllamaEmbeddings(
    model =selected_llm_name.split()[0].lower(),
    base_url = "http://127.0.0.1:11434"
      )

**Vector Store:** Chroma is used to store processed document embeddings persistently.

.. highlight:: python

    persist_directory = r"C:\Users\PC\anaconda3\envs\rag_env\Lib\site-packages\chromadb"
    vector_store = Chroma(persist_directory=persist_directory, embedding_function = embed_model)


3. Document Processing
-----------------------
PDFs are uploaded and processed using:
PyPDFLoader: Loads content from PDF files.
RecursiveCharacterTextSplitter: Splits documents into chunks of 500 characters for indexing.
Processed chunks are added to the Chroma vector store.

4. Retrieval-Augmented Generation (RAG) Chain
----------------------------------------------
**Retriever:** Fetches relevant documents from the vector store using similarity search.

.. highlight:: python

    retriever = vector_store.as_retriever(search_kwargs={"k":5})


**QA Chain:** Combines retrieved documents with the input query to generate context-aware answers using the selected LLM.

.. highlight:: python

    def custom_qa_prompt(context,input):
    if context:
        return f"Voici le contexte extrait du PDF : {context}. Maintenant, réponds à la question : {input}"
    else:
        return f"Je n'ai trouvé aucun contexte pertinent dans le PDF. donne une réponse courte et directesur la question suivante : {input}"

    # Wrap the custom_qa_prompt in a PromptTemplate
    qa_prompt_template = PromptTemplate(
        input_variables=["input", "context"],
        template=custom_qa_prompt("{input}", "{context}")
    )

    
5. Streamlit Interface
----------------------
File Uploader: Handles PDF uploads.
Text Input: Accepts user questions.
Button Actions: Triggers PDF processing or question answering.