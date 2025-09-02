# Chat with Internal Documents (RAG AI Agent)

Enables context-aware chat over internal documents using n8n, Ollama, and Supabase Vector DB.

## Features
- Answers limited to provided documents
- Retrieval-Augmented Generation (RAG) with Supabase
- Multi-format file support: PDF, Excel, Google Docs, text
- Automated ingestion from Google Drive
- Real-time updates
- Embedding generation via Ollama
- Memory-enabled agent using PostgreSQL
- Custom tools for document lookup

## How It Works

### Document Ingestion & Vectorization
- Watches Google Drive folder for new/updated files
- Deletes old vector entries
- Extracts content from PDF, Excel, Docs, or text
- Summarizes/preprocesses content
- Splits and embeds text via Ollama
- Stores embeddings in Supabase Vector DB

### RAG Chat Agent
- Chat via Webhook or built-in interface
- User input sent to RAG Agent
- Queries Supabase vector store for relevant content
- Answers with context if found, else calls tools or requests clarification
- Responses stored in PostgreSQL for memory

## Supabase Setup
1. Create a Supabase project at https://supabase.com
2. Create a `documents` table:

