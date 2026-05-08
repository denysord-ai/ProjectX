# Project Context

## Project Name
ProjectX

## Project Goal
Build a web application with API connection to the ChatGPT, Claude and Gemini and learn how to use their functionality.

The system in MVP version should allow users to:
- upload a PDF
- ask questions about PDF content
- receive AI-generated answers
- compare answers from different AI providers later

## Learning Goal
This project is a learning path for:
- AI provider APIs
- Python
- FastAPI
- NiceGUI
- API design
- async programming
- file uploads
- clean architecture
- testing
- RAG and document indexing later
- deployment basics

## Core MVP Features
- Upload one PDF
- Ask one question about the PDF
- Get an answer from one AI provider
- Display result in web UI
- Store basic document metadata
- Store question/answer history

## Supported AI Providers

### MVP
- OpenAI

### Later
- Gemini
- Claude

## Tech Stack

### Backend
- Python 3.14+
- uv
- FastAPI
- Pydantic
- SQLAlchemy or SQLModel
- Alembic

### Frontend
- NiceGUI as primary Python frontend

### Storage
- PostgreSQL for metadata and history
- Local file storage for PDFs initially

### Future Infrastructure
- Vector DB or provider-native file search for RAG
- Docker
- CI/CD

## Architecture Principles
- API-first
- Provider-agnostic
- Clean separation of layers
- Simple MVP first
- Avoid premature abstractions
- Keep AI provider logic isolated

## Main Layers
- UI layer
- API layer
- Application services
- Domain models
- AI providers
- Infrastructure
- Storage
- Database

## Provider Abstraction
The system should hide provider-specific details behind a common interface.

Example providers:
- OpenAIProvider
- GeminiProvider
- ClaudeProvider

Common operation:
- ask_pdf(document, question) -> answer

## Key Entities
- Document
- Question
- Answer
- Provider
- Model
- Conversation
- UserSettings, later if needed

## MVP Non-Goals
The first version should NOT include:
- authentication
- payments
- multi-user permissions
- complex RAG
- custom embeddings
- cloud deployment
- advanced UI
- streaming responses
- background queues

## MVP Definition of Done
MVP is done when:
- user can upload a PDF
- uploaded file is saved locally
- document metadata is saved to PostgreSQL
- user can ask a question
- backend sends PDF + question to OpenAI
- answer is displayed in NiceGUI
- question and answer are saved
- project can be started from README instructions

## Roadmap

### v0.1 — OpenAI PDF QA
- FastAPI backend
- NiceGUI frontend
- PDF upload
- ask question
- get answer from OpenAI
- save history

### v0.2 — Multi-provider Support
- add Gemini
- add Claude
- provider selector
- model selector

### v0.3 — Compare Mode
- one PDF
- one question
- answers from OpenAI, Gemini, Claude side by side

### v0.4 — Document History
- list uploaded documents
- reopen document
- view previous questions and answers
- regenerate answer

### v0.5 — Summaries
- summarize PDF
- extract key points
- extract action items
- maybe generate quiz/questions

### v0.6 — RAG / Indexing
- indexed documents
- multi-question conversations
- citations/page references
- larger PDFs

## Open Questions
- Should PDF files stay local or move to S3/MinIO?
- Should we use provider-native file search or custom RAG?
- Should each provider have separate document upload logic?
- How should we track token usage and cost?
- Do we need streaming responses in the UI?
