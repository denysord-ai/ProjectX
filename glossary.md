# Glossary

Project-local terms used across ProjectX files, ADRs, and conversations.

Add a term when:
- It's used in multiple files or analyses and has specific technical meaning
- A reader six months from now might not immediately know what we mean
- It comes from an external source we want to attribute

Order: alphabetical for lookup. New terms can be inserted anywhere
in alphabetical order.

---

## RAG — Retrieval-Augmented Generation

It is a pattern where an AI model answers a question using external knowledge retrieved at query time, instead of 
relying only on what the model already "knows". Search engine + AI writer.

**Simple example**  
Without RAG:  
User question → AI model → answer

With RAG:  
User question
   ↓
Retrieve relevant PDF fragments
   ↓
Send fragments + question to AI model
   ↓
Answer grounded in those fragments

---
