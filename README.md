# YouTube Chatbot using LangChain: Building a RAG System

## Summary

A Retrieval-Augmented Generation (RAG) chatbot that enables users to interact with YouTube videos in real-time, generate summaries, and ask context-aware questions directly from video transcripts.

---

# Overview

This project demonstrates the implementation of a Retrieval-Augmented Generation (RAG) architecture using LangChain and OpenAI models. The application extracts YouTube video transcripts, converts them into searchable vector embeddings, and uses a Large Language Model (LLM) to answer user questions based only on the video content.

The system helps users quickly understand long-form video content such as podcasts, interviews, lectures, and tutorials without watching the entire video.

---

# Problem Statement

Long YouTube videos often contain valuable information, but finding specific insights within hours of content can be difficult and time-consuming.

This project solves that problem by allowing users to:

* Ask questions directly about a video
* Generate concise summaries
* Get point-wise explanations
* Retrieve important insights instantly

The chatbot responds using only the transcript context, reducing hallucinations and improving answer relevance.

---

# Dataset

The dataset used in this project is dynamic and generated from YouTube video transcripts.

The transcripts are fetched using the YouTube Transcript API and include:

* Video text content
* Time-stamps
* Sequential transcript segments

These transcript chunks are processed and converted into embeddings for semantic search and retrieval.

---

# Tools and Technologies

### Framework

* LangChain

### LLM & Embeddings

* OpenAI GPT Models
* OpenAI Embeddings

### Data Fetching

* YouTube Transcript API

### Vector Database

* FAISS

### Text Processing

* RecursiveCharacterTextSplitter

### Development Environment

* Google Colab
* Python

### Suggested Frontend/UI

* Streamlit
* HTML/CSS/JavaScript
* Chrome Extension Integration

---

# Methods

The project follows a standard RAG pipeline implemented using LangChain Expression Language (LCEL).

## 1. Indexing

* Fetch YouTube transcript using Video ID
* Split transcript into smaller chunks
* Generate embeddings using OpenAI Embeddings
* Store embeddings in FAISS vector database

## 2. Retrieval

* Perform similarity search on the vector store
* Retrieve the most relevant transcript chunks based on user queries

## 3. Augmentation

* Combine retrieved chunks into contextual input
* Use a prompt template instructing the LLM to answer strictly from context

## 4. Generation

* Send augmented prompt to the OpenAI model
* Generate context-aware responses

## 5. Chaining

* Combine retrieval and generation using LangChain LCEL
* Use RunnableParallel for parallel context and query handling

---

# Key Insights

* The YouTube Transcript API provided more reliable transcript extraction than default LangChain loaders.
* The chatbot supports multilingual transcripts, including Hindi and other languages.
* Using vector embeddings significantly improves semantic retrieval quality.
* Parallel chains improve performance by efficiently managing context and queries simultaneously.
* Context-restricted prompting helps reduce hallucinated answers.

---

# Dashboard / Model / Output

The project currently runs inside Google Colab as an interactive chatbot.

### Features

* Real-time question answering
* Bullet-point video summaries
* Topic-specific explanations
* Context-aware responses
* Fallback responses such as “I don’t know” when information is unavailable

### Example Use Cases

* Summarizing podcasts
* Extracting AI or technology insights
* Understanding lectures quickly
* Retrieving specific moments from long videos

---

# How to Run This Project

## 1. Clone the Repository

```bash
git clone <your-repository-link>
```

## 2. Install Required Libraries

```bash
pip install langchain openai faiss-cpu youtube-transcript-api
```

## 3. Add OpenAI API Key

```python
OPENAI_API_KEY = "your_api_key"
```

## 4. Enter YouTube Video ID

Example:

```python
video_id = "xxxxxxxxxxx"
```

## 5. Run the Notebook

* Execute transcript indexing cells
* Run vector embedding generation
* Start asking questions using:

```python
main_chain.invoke("Your Question")
```

---

# Results & Conclusion

The project successfully demonstrates a functional RAG-based chatbot capable of understanding and interacting with YouTube video content.

The system:

* Improves accessibility of long-form video content
* Enables efficient information retrieval
* Demonstrates practical use of LangChain and vector databases
* Provides accurate context-aware responses

---

# Future Enhancements

Future improvements may include:

* Streamlit web application deployment
* Agentic RAG implementation
* Multimodal capabilities
* RAGAS evaluation metrics
* Hybrid search and re-ranking
* Memory-enabled conversational chatbot
* Chrome extension integration

---

# Author

Manika Rajput

