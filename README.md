# RAG-Based Question Answering System

## 📌 Project Overview
This project implements a **Retrieval-Augmented Generation (RAG)** based Question Answering system.

Users can upload documents and ask questions, and the system generates answers **only from the content of the uploaded documents**. The approach combines vector-based retrieval with a local language model to produce grounded and context-aware responses.

---

## 🎯 Objective
- Enable question answering over user-provided documents  
- Retrieve relevant document chunks using semantic similarity  
- Generate accurate answers using a local Large Language Model (LLM)  

---

## ✨ Features
- Supports **PDF** and **TXT** documents  
- Document chunking and embedding generation  
- Vector storage and similarity search using **FAISS**  
- Context-aware answer generation using a **local LLM**  
- **Latency tracking** for question–answer generation  
- Simple, notebook-based implementation with **API-ready structure**

---

## 🧠 System Workflow
1. Upload documents  
2. Split documents into overlapping chunks  
3. Generate embeddings for each chunk  
4. Store embeddings in a FAISS vector index  
5. Retrieve top relevant chunks based on query similarity  
6. Generate answers using retrieved context and a local LLM  

---

## 🧩 Chunking Strategy
- **Chunk size:** 500 characters  
- **Overlap:** 50 characters  

### Why this approach?
- Captures focused context  
- Preserves semantic meaning  
- Reduces the risk of missing answers split across chunks  

---

## ⚠️ Observed Retrieval Limitation
For very generic questions (for example, *"Explain everything"*), the retriever may return less relevant chunks due to similar embedding scores.

This highlights the importance of:
- Well-phrased user queries  
- Applying **top-k filtering** during retrieval  

---

## 📊 Metrics Tracked
- **Latency (seconds)** for each question–answer generation  

### Why latency matters
- Critical for real-time and interactive applications  
- Helps evaluate system responsiveness and performance  

---

## 🛠️ Tech Stack
- Python  
- SentenceTransformers (Embeddings)  
- FAISS (Vector Store)  
- HuggingFace Transformers  
- Jupyter Notebook  

---

## ▶️ How to Run
1. Install the required Python dependencies  
2. Open the notebook  
3. Upload documents  
4. Ask questions based on document content  

---

## 📌 Conclusion
This project demonstrates a practical implementation of a Retrieval-Augmented Generation system using vector similarity search and a local language model. It highlights the effectiveness of combining retrieval with generation for document-based question answering.
