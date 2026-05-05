

#  YouTube Chatbot using LangChain (RAG System)

##  Summary

This project is a simple chatbot that lets you talk to YouTube videos.
You can paste a video ID, ask questions, and get answers based only on what is spoken in the video.

It uses a Retrieval-Augmented Generation (RAG) pipeline built with LangChain and OpenAI.

---

# Overview

Long YouTube videos are hard to go through when you just need specific information.

This project solves that by turning a video into a searchable knowledge base.

It:

* pulls the transcript from YouTube
* breaks it into chunks
* converts it into embeddings
* stores it in a vector database (FAISS)
* uses an LLM to answer questions from that content

So instead of watching the full video, you can just ask questions.

---

#  Problem it solves

Most YouTube videos (lectures, podcasts, tutorials) are long.

Finding one small answer means:

* scrubbing through the video
* guessing timestamps
* wasting time

This chatbot removes that problem by letting you ask directly:

* “Summarize this video”
* “What is the main idea?”
* “Explain this topic”

---

#  Tools used

* LangChain
* OpenAI (GPT + Embeddings)
* YouTube Transcript API
* FAISS (vector database)
* Python
* Jupyter Notebook

---

#  How it works

### 1. Get transcript

We extract the transcript from a YouTube video using its ID.

### 2. Split text

The transcript is split into smaller overlapping chunks so it’s easier to search.

### 3. Convert to embeddings

Each chunk is converted into vectors using OpenAI embeddings.

### 4. Store in FAISS

All vectors are stored in a FAISS index for fast similarity search.

### 5. Retrieve relevant context

When a question is asked, we find the most relevant chunks.

### 6. Generate answer

The LLM answers using only the retrieved context.

---

#  Features

* Ask questions about any YouTube video
* Get instant summaries
* Context-based answers only (no guessing)
* Works inside Jupyter Notebook
* Handles long videos easily

---

#  How to run

## 1. Clone the repo

```bash
git clone https://github.com/mr10825060/YouTube-Q-A-Chatbot-using-RAG
cd YouTube-Q-A-Chatbot-using-RAG
```

---

## 2. Install dependencies

```bash
pip install langchain langchain-community langchain-openai faiss-cpu youtube-transcript-api tiktoken openai
```

---

## 3. Open Jupyter Notebook

```bash
jupyter notebook
```

Then open the `.ipynb` file you uploaded.

---

## 4. Add OpenAI key

```python
import os
os.environ["OPENAI_API_KEY"] = "your_api_key"
```

---

## 5. Run step by step

Run all cells in order:

* transcript extraction
* chunking
* embeddings
* FAISS index
* retriever
* chatbot chain

---

## 6. Ask questions

```python
main_chain.invoke({
    "question": "Summarize the video"
})
```

---

#  What this project shows

This is basically a working RAG pipeline applied to real YouTube content.

It shows:

* how retrieval + LLMs work together
* how vector databases improve search
* how to build a real-world AI chatbot

---

#  Future improvements

* Add Streamlit UI
* Support multiple videos
* Add memory (chat history)
* Show timestamps from video
* Deploy online

---

#  Author

Manika Rajput

---

