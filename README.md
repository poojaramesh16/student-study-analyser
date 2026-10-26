🎓Student Study Analyser

An AI-Powered PDF Question Answering System Using Retrieval-Augmented Generation (RAG)

About the Project

Student Study Analyser is an AI-powered study assistant that allows users to upload PDF study materials and ask questions about their contents.

The application uses Retrieval-Augmented Generation (RAG) to retrieve relevant information from the uploaded document and generate context-based answers using a language model.

The project demonstrates how document processing, semantic search, vector databases, and Large Language Models (LLMs) can be combined to build an interactive AI application.

Objectives

- Simplify the process of finding information in study materials.
- Enable users to ask questions in natural language.
- Retrieve relevant information from uploaded PDF documents.
- Generate answers using the retrieved document context.
- Explore the practical implementation of a RAG-based AI application.

Features

- PDF Upload: Upload study materials in PDF format.
- Text Extraction: Extract readable text using PyPDF.
- Text Chunking: Divide extracted text into smaller, overlapping chunks.
- Text Embeddings: Convert text chunks into numerical representations using Sentence Transformers.
- Semantic Retrieval: Retrieve relevant text chunks using ChromaDB.
- AI-Powered Answers: Generate context-based responses using the Qwen instruction-tuned language model.
- Interactive Chat Interface: Interact with the uploaded document through a Gradio interface.
- Context-Aware Responses: Instruct the model to acknowledge when the PDF does not provide enough information.

Technologies Used

Technology| Purpose
Python| Core programming language
Google Colab| Development and execution environment
PyPDF| Extracting text from PDF documents
LangChain Text Splitters| Splitting text into manageable chunks
Sentence Transformers| Generating text embeddings
ChromaDB| Storing and retrieving document embeddings
Hugging Face Transformers| Loading and running the language model
Qwen2.5 Instruct| Generating answers from retrieved context
PyTorch| Supporting model inference
Gradio| Building the interactive user interface
Accelerate| Supporting model device placement

How It Works

The application follows a Retrieval-Augmented Generation (RAG) pipeline.

1. Upload PDF: The user uploads a study document.
2. Extract Text: PyPDF extracts readable text from the document.
3. Chunk the Text: The extracted text is split into chunks of 1,000 characters, with an overlap of 200 characters.
4. Generate Embeddings: Sentence Transformers converts the chunks into vector representations.
5. Store Embeddings: ChromaDB stores the chunks and their embeddings.
6. Retrieve Relevant Context: The user's question is converted into an embedding, and the three most relevant chunks are retrieved, or fewer if the collection contains fewer chunks.
7. Generate an Answer: The Qwen language model receives the retrieved context and question and generates a response.
8. Display the Result: Gradio displays the response in an interactive chat interface.

Architecture

PDF Document
↓
Text Extraction using PyPDF
↓
Text Chunking
↓
Embedding Generation
↓
ChromaDB Vector Storage
↓
Question Embedding and Semantic Retrieval
↓
Relevant Context + User Question
↓
Qwen2.5 Instruct Language Model
↓
Generated Answer
↓
Gradio Chat Interface

How to Run the Project

Prerequisites

- A Google account.
- Access to Google Colab.
- An internet connection to install dependencies and download the required models.
- A suitable runtime with sufficient memory for the language model.

Steps

1. Open the notebook "student_study_analyser.ipynb" from this repository.
2. Open it in Google Colab.
3. Run the notebook cells in order.
4. Allow the required Python libraries and models to download.
5. Upload a PDF containing readable text.
6. Click Process PDF.
7. Wait for the processing confirmation.
8. Enter a question about the uploaded document.
9. Click Send to receive an AI-generated answer.

A GPU runtime may be needed depending on available memory and the selected language model.

What I Learned

Through this project, I explored:

- The fundamentals of Retrieval-Augmented Generation.
- PDF text extraction and preprocessing.
- Text chunking and overlap.
- Semantic embeddings and similarity-based retrieval.
- Vector database operations using ChromaDB.
- Integration of a language model with retrieved context.
- Prompt design for document-grounded question answering.
- Building an interactive AI application using Gradio.
- Combining multiple AI libraries into a single workflow.

Limitations

- Answer quality depends on the PDF's readable text and the relevance of the retrieved chunks.
- Scanned PDFs may require OCR, which is not implemented in the current version.
- The language model can still generate incorrect or incomplete answers.
- The current ChromaDB setup is in-memory, so the document collection is not designed to persist across runtime restarts.
- Model downloads and inference require sufficient memory and computational resources.
- The Gradio share link generated from Colab is temporary and should not be treated as a permanent deployment.
- The current notebook is a prototype and is not yet configured as a production-ready application.

Future Improvements

- Add OCR support for scanned documents.
- Display source passages alongside answers.
- Improve retrieval accuracy and evaluate answer quality.
- Add support for multiple PDF documents.
- Persist document embeddings between sessions.
- Add document summaries and automatic generation of study questions.
- Deploy the application using a suitable hosting platform.

Project Information

Project: Student Study Analyser
Category: Generative AI | Natural Language Processing | RAG
Development Environment: Google Colab
Interface: Gradio

---

This project was developed as a learning exercise to explore practical applications of Retrieval-Augmented Generation and document-based question answering.
