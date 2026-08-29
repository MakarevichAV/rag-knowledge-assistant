# RAG Knowledge Assistant

Full-stack RAG (Retrieval-Augmented Generation) application for building and querying a document-based knowledge base using natural language.

The system allows users to upload documents, automatically index their content, ask questions, and receive AI-generated answers grounded in the stored knowledge with source references.

## Features

- Document upload and management
- Automatic text chunking and vector indexing
- Semantic search using vector embeddings
- RAG-based question answering
- Source attribution for generated answers
- Automatic knowledge-base rebuilding after document changes
- Web interface for interacting with the knowledge base

## Architecture

User
  ↓
React UI
  ↓ REST API
FastAPI
  ↓
RAG Service
  ├── LangChain
  ├── Ollama Embeddings
  ├── Ollama LLM
  └── PostgreSQL + pgvector

## Tech Stack

**Frontend:** React, JavaScript, Vite  
**Backend:** Python, FastAPI  
**RAG:** LangChain  
**LLM & Embeddings:** Ollama  
**Vector Database:** PostgreSQL, pgvector  
**Infrastructure:** Docker

## Repositories

### Backend

**rag-assistant-api**

FastAPI backend implementing document management, vector indexing, semantic retrieval and RAG-based answer generation.

→ [View Backend Repository](https://github.com/MakarevichAV/rag-assistant-api)

### Frontend

**rag-assistant-ui**

React frontend for managing knowledge-base documents, asking questions and displaying generated answers with their sources.

→ [View Frontend Repository](https://github.com/MakarevichAV/rag-assistant-ui)

## How It Works

1. Documents are uploaded to the knowledge base.
2. Documents are split into chunks and converted into vector embeddings.
3. Embeddings are stored in PostgreSQL using pgvector.
4. A user submits a natural-language question.
5. Relevant document chunks are retrieved using semantic similarity.
6. The retrieved context is provided to the LLM.
7. The generated answer is returned together with its source references.

## Project Structure

The application is split into two independent repositories:

- [rag-assistant-api](https://github.com/MakarevichAV/rag-assistant-api) — backend, RAG pipeline and vector storage
- [rag-assistant-ui](https://github.com/MakarevichAV/rag-assistant-ui) — React web interface

This repository serves as the main overview and entry point for the complete project.
