# RAG-Based Question Answering System

## Objective
This project implements a Retrieval-Augmented Generation (RAG) based Question Answering system.  
Users can upload documents and ask questions based only on the content of those documents.

The system retrieves relevant document chunks using embeddings and similarity search, then generates answers using a local LLM.

---

## Features
- Supports PDF and TXT documents
- Document chunking and embedding
- Vector storage using FAISS
- Similarity-based retrieval
- Local LLM-based answer generation
- Latency tracking
- Simple API-ready design

---

## Tech Stack
- Python
- SentenceTransformers (Embeddings)
- FAISS (Vector Store)
- HuggingFace Transformers
- Jupyter Notebook
- FastAPI (API-ready structure)

---

## Chunking Strategy
- Chunk size: **500 characters**
- Overlap: **50 characters**

### Why this chunk size?
- Small enough to capture specific context
- Large enough to preserve meaning
- Prevents missing answers split across chunks

---

## Retrieval Failure Case
When a question was very generic (example: *"Explain everything"*),  
the retriever returned unrelated chunks because similarity scores were close.

This showed the importance of:
- Better query phrasing
- Adding top-k filtering

---

## Metric Tracked
**Latency (seconds)** was tracked for each question-answer generation.

Why latency?
- Important for real-time applications
- Helps measure system responsiveness

---

## How to Run

1. Install dependencies:
