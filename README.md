# FCAI Regulations RAG API

A RAG API for querying the USC Faculty of Computer and Artificial Intelligence Internal Regulations using Google Gemini and ChromaDB. Supports bilingual queries in English and Arabic.

## Live Demo

- **API Endpoint**: https://ahmed-ayman-fcai-usc-regulations-chatbot-api.hf.space
- **Hugging Face Space**: https://huggingface.co/spaces/ahmed-ayman/fcai-usc-regulations-chatbot-api

## Tech Stack

- Flask
- Google Gemini 2.5 Flash
- HuggingFace multilingual-e5-base embeddings
- ChromaDB vector store
- LangChain

## Setup

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Set your Google API key:
```bash
export GOOGLE_API_KEY="your-api-key-here"
```

3. Run the application:
```bash
python app.py
```

The API will start on `http://0.0.0.0:7860`

## Docker

```bash
docker build -t fcai-rag-api .
docker run -p 7860:7860 -e GOOGLE_API_KEY="your-key" fcai-rag-api
```

## API Usage

**Health Check:**
```bash
GET /
```

**Query Endpoint:**
```bash
POST /api/chat
Content-Type: application/json

{
  "query": "What are the admission requirements?"
}
```

Response includes the answer and source citations from the regulations document.
