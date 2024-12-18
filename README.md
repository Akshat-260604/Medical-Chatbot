This repository presents a medical chatbot capable of answering health-related questions by retrieving relevant information from a collection of medical PDFs. The chatbot is built using the LangChain framework, which facilitates document processing and retrieval using advanced AI techniques. It employs Hugging Face sentence embeddings for semantic understanding of text and FAISS for efficient similarity search. The chatbot leverages a pre-trained language model, LLaMA-2, to generate factually accurate and context-aware responses.

Features
The chatbot offers several key features:

PDF Document Support: It can load and process multiple medical PDFs, extracting content for further analysis.

Efficient Search Mechanism: The chatbot uses FAISS, a highly efficient vector search system, allowing it to find the most relevant document segments quickly.

Embeddings for Context Understanding: The chatbot utilizes Hugging Face’s sentence-transformers/all-MiniLM-L6-v2 model to generate embeddings, which are numerical representations of the text that preserve the semantic meaning.

Generative Responses: LLaMA-2, a powerful pre-trained model, generates responses to user queries based on the information retrieved from the medical documents.

Interactive Chat Interface: The chatbot operates in an interactive loop, enabling users to ask questions in real-time and receive detailed answers.

Installation and Setup
To begin, users should clone the repository and install the necessary dependencies listed in the requirements.txt file. This includes libraries like LangChain, FAISS, and Annoy, which are required for document embedding, search, and retrieval processes. Once installed, the user can load medical PDF documents by placing them in a designated data/ folder. The chatbot will process these PDFs and extract text data.

Document Processing
The first stage involves loading the medical PDFs using a document loader, which extracts the content from each file. These documents are then split into smaller, manageable text chunks. This text-splitting process ensures that large documents are divided into sections that the system can handle more efficiently during the search and retrieval process.

Embedding Generation and FAISS Indexing
Once the text chunks are created, the chatbot generates embeddings for each chunk using Hugging Face's sentence transformers. These embeddings serve as numerical representations of the document's content, capturing its semantic meaning. The FAISS vector store indexes these embeddings to allow for quick and relevant similarity-based search. This indexing process is crucial because it enables the chatbot to rapidly retrieve the most relevant chunks of information when a user asks a question.

Question-Answering Process
The core functionality of the chatbot revolves around its ability to answer user questions by retrieving relevant context from the medical PDFs. When a user inputs a query, the chatbot uses the FAISS vector store to search for document chunks that closely match the query. It then passes the retrieved content to the LLaMA-2 language model, which generates a coherent and factually accurate response. The chatbot also uses a custom prompt template to ensure that the responses are precise and informative without any fabricated content.

Limitations: LLaMA-2 Model Size
One notable limitation is that the pre-trained LLaMA-2 model used in this chatbot could not be uploaded to this repository due to its large size. The model files exceed standard GitHub size limits, which prevents their direct inclusion. As such, users will need to manually download the LLaMA-2 model from appropriate sources, as outlined in the code documentation.

The chatbot operates in an interactive chat loop, where users can input questions and receive answers in real-time. The bot continues this conversation until the user decides to exit the session. This real-time interaction makes the chatbot useful for retrieving medical information quickly and efficiently.


The chatbot is highly customizable. Users can replace the medical PDFs with any other documents to adjust the knowledge base. Additionally, they can swap the Hugging Face model used for embedding generation or tweak the parameters of the language model to suit different use cases. These adjustments allow the chatbot to be flexible and adaptable to different domains beyond the medical field.


This medical chatbot represents a robust solution for interacting with large medical texts and retrieving relevant information in response to user queries. It combines advanced document processing techniques with state-of-the-art language models to deliver accurate and contextually rich responses. While the large size of the LLaMA-2 model presents some challenges for sharing the complete setup, the chatbot’s modular architecture ensures that it remains flexible and scalable for a wide range of applications.

