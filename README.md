# MultiModal Retrieval-Augmented Generation (RAG)

## Overview
This project implements a **multimodal RAG pipeline** capable of combining **text and image embeddings** to retrieve and generate answers from documents containing both modalities (e.g., PDFs with diagrams, scanned floorplans, reports). It enables advanced question-answering and search on heterogeneous datasets.

## Features
- **Multimodal Support:** Combines embeddings from both text and images for unified retrieval.
- **Recursive Text Chunking:** Splits text into overlapping segments to retain context across boundaries.
- **Vector Database Integration:** Stores multimodal embeddings (FAISS/Chroma) for fast semantic search.
- **Flexible Input:** Works on PDFs, images, and OCR-processed documents.
- **RAG Pipeline:** Retrieved chunks (text + image) are fused into prompts for LLM-based generation.

## Tech Stack
- Python
- Pillow (PIL)
- LangChain for orchestration
- OpenAI / Hugging Face embeddings (text + image)
- FAISS / Chroma for vector storage
- Google Colab / Jupyter Notebook for development

## Architecture
1. **Data Ingestion**
   - Extract text and images from PDFs or standalone files.
   - Process text using recursive chunking with overlap.
   - Generate OCR for images if needed.

2. **Embedding & Storage**
   - Text: `text-embedding-3-large` or similar
   - Images: CLIP or Vision Transformer embeddings
   - Store in vector database with metadata

3. **Querying**
   - Convert user query (text/image) into embeddings
   - Retrieve top‑k multimodal chunks
   - Compose RAG prompt and generate contextual response

## Setup
```bash
git clone <repo-url>
cd multimodal-rag
pip install -r requirements.txt
```
Set API keys (e.g., OpenAI) in `.env` or Colab cell.

## Usage
Run the Jupyter Notebook:
```bash
jupyter notebook MultiModalRag.ipynb
```
Or use in Google Colab by uploading the notebook and following instructions.

## Applications
- Intelligent PDF QA (research papers, manuals, reports)
- Floorplan and architectural document analysis
- Multimodal document search (contracts, scanned documents)

## Future Enhancements
- Hybrid scoring between text and image embeddings
- Real-time API deployment (FastAPI/Streamlit)
- Support for large PDF datasets with memory optimization

## License
MIT License
