# 📄 Multimodal RAG for PDF Intelligence (Single Notebook)

This project demonstrates a **Multimodal Retrieval-Augmented Generation (RAG)** pipeline implemented **entirely within a single Jupyter Notebook (`.ipynb`)**.

It enables intelligent extraction and reasoning over **PDF documents containing both text and images** (charts, tables, scanned pages) by combining:

- **CLIP (Hugging Face)** for multimodal embeddings (text + images)
- **PyMuPDF** for PDF parsing
- **OpenAI GPT-4o** for reasoning and data extraction

---

## 🚀 Why Multimodal RAG?

Most PDFs are **not purely textual**. They often contain:
- Charts & graphs
- Tables embedded as images
- Scanned documents
- Visual cues essential for interpretation

Traditional text-only RAG fails in these scenarios.

This notebook implements **Multimodal RAG**, where:
- Text and images are embedded into the **same vector space**
- Relevant multimodal context is retrieved
- GPT-4o reasons across **both text and visual information**

---

## 🧠 What This Notebook Does

✔ Reads PDFs using PyMuPDF  
✔ Extracts text and images page-by-page  
✔ Generates multimodal embeddings using CLIP  
✔ Stores embeddings in a vector index  
✔ Retrieves relevant multimodal context for a query  
✔ Uses GPT-4o to generate grounded answers  

All inside **one notebook**.

---

## 🏗️ Architecture Overview

```text
PDF
 ├── Text  ──► CLIP Text Encoder ──┐
 ├── Images ─► CLIP Image Encoder ─┼──► Vector Index ─► Retriever
                                   │
User Query ────────────────────────┘
                                        │
                                        ▼
                               GPT-4o (Reasoning)
                                        │
                                        ▼
                              Structured / Free-text Output
