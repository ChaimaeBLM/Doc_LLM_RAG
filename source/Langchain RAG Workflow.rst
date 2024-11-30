LangChain RAG Workflow
=======================

______________________

Step 1: LLM Initialization
--------------------------
The user selects an LLM `Llama3 or Mistral` via the Streamlit dropdown.
The app initializes the selected model using Ollama.

Step 2: PDF Upload and Chunking
-------------------------------
The uploaded PDF is loaded using PyPDFLoader.
The document is split into smaller chunks using `RecursiveCharacterTextSplitter` to optimize retrieval.

Step 3: Vector Store Creation
------------------------------
Document chunks are embedded using `OllamaEmbeddings` and stored in the Chroma vector database for future queries.

Step 4: Query Workflow
-----------------------
The user inputs a question.
The Retriever fetches the top 5 most relevant document chunks based on similarity.
The QA Chain:
Combines the retrieved context with the user query.
Uses a custom prompt `custom_qa_prompt` to format the input for the LLM.
Generates a response via the selected LLM.

Step 5: Output Display
------------------------
The app displays the answer:
If context is available, the response includes information extracted from the PDF.
Otherwise, a brief direct response is generated.