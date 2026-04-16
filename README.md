# 🚀 FastAPI Financial Document Management with Semantic Analysis (RAG)

## 📌 Overview

This project is a **Financial Document Management System** built using **FastAPI** with **AI-powered semantic search (RAG - Retrieval Augmented Generation)**.

It allows organizations to:

* Upload and manage financial documents
* Store metadata (company, type, etc.)
* Perform **semantic search** using AI (not just keyword search)
* Retrieve meaningful financial insights from documents

---

## 🧠 Key Features

### 🔐 Authentication & Security

* User Registration & Login (JWT-based authentication)
* Role-based access (Admin, Analyst, Auditor, Client)

### 📄 Document Management

* Upload financial documents
* Store metadata:

  * document_id
  * title
  * company_name
  * document_type (invoice, report, contract)
  * content
* Retrieve and delete documents
* Search documents using metadata

### 🤖 RAG (AI Semantic Search)

* Document → Chunking → Embedding → Vector DB

* Query → Embedding → Similarity Search → Results

* Uses:

  * Sentence Transformers (Embeddings)
  * FAISS (Vector Database)

### 🔍 Semantic Search

* Understands **meaning**, not just keywords
* Example:

  * Query: *"financial risk due to debt"*
  * Finds: *"high debt ratio"*

---

## ⚙️ Tech Stack

* **Backend**: FastAPI
* **Database**: SQLite
* **Vector DB**: FAISS
* **Embeddings**: Sentence Transformers
* **Authentication**: JWT (python-jose)
* **Deployment**: Google Colab + ngrok

---

## 🔄 System Architecture

```
Document Upload
      ↓
Text Extraction
      ↓
Chunking
      ↓
Embeddings
      ↓
FAISS Vector Store
      ↓
User Query
      ↓
Embedding
      ↓
Similarity Search
      ↓
Top Relevant Results
```

---

## 📡 API Endpoints

### 🔐 Authentication

| Method | Endpoint       | Description       |
| ------ | -------------- | ----------------- |
| POST   | /auth/register | Register user     |
| POST   | /auth/login    | Login and get JWT |

---

### 📄 Documents

| Method | Endpoint          | Description        |
| ------ | ----------------- | ------------------ |
| POST   | /documents/upload | Upload document    |
| GET    | /documents        | Get all documents  |
| GET    | /documents/{id}   | Get document       |
| DELETE | /documents/{id}   | Delete document    |
| GET    | /documents/search | Search by metadata |

---

### 🤖 RAG APIs

| Method | Endpoint            | Description               |
| ------ | ------------------- | ------------------------- |
| POST   | /rag/index-document | Add document to vector DB |
| POST   | /rag/search         | Semantic search           |
| GET    | /rag/context/{id}   | Get document context      |

---

## 🧪 Example Outputs

### ✅ 1. Register User

```json
{
  "msg": "User registered"
}
```

---

### 🔑 2. Login

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

---

### 📄 3. Upload Document

```json
{
  "msg": "Document stored"
}
```

---

### 🔍 4. Semantic Search

**Request:**

```json
{
  "query": "financial risk due to debt"
}
```

**Response:**

```json
{
  "results": [
    "high debt ratio indicates risk",
    "financial instability due to loans"
  ]
}
```

---

### 📚 5. Get Documents

```json
[
  {
    "id": 1,
    "title": "Annual Report",
    "company_name": "TCS",
    "document_type": "report"
  }
]
```

---

## 🚀 How to Run

### ▶️ Run in Google Colab

1. Install dependencies

```bash
pip install fastapi uvicorn faiss-cpu sentence-transformers python-jose sqlalchemy pyngrok nest-asyncio
```

2. Run FastAPI server

3. Use ngrok to expose API

4. Open:

```
https://your-ngrok-link/docs
```

---

## 🔐 Security Best Practices

* Do NOT expose:

  * ngrok token
  * JWT secret keys
  * database files

* Use `.env` for sensitive data

---

## 📌 Use Cases

* Banking systems
* Financial audits
* Risk analysis tools
* Document intelligence platforms

---

## 🎯 Project Highlights

✔ Full FastAPI backend
✔ JWT Authentication
✔ Role-based system
✔ RAG pipeline implementation
✔ Semantic search with FAISS
✔ Real-world AI application

---

## 💬 Interview Explanation

> This project implements a financial document management system using FastAPI with RAG-based semantic search. It uses embeddings and FAISS to retrieve meaningful insights from documents, along with JWT authentication and structured APIs.

---

## 👨‍💻 Author

**Prateek Tiwari**

---

⭐ If you found this project useful, give it a star!
