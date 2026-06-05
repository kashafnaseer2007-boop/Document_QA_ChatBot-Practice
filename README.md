# 📄 Document Q&A ChatBot

Ask questions about any PDF document and get answers **only from its content**. Built with **Streamlit**, **LangChain**, **FAISS**, and **Groq's Llama 3**.

## ✨ Features

- Upload a PDF (any size).
- Ask natural language questions.
- Answers are **grounded only in your document** – no hallucinations.
- Fast responses using Groq's Llama 3 API.
- Fully local embeddings using Hugging Face's BGE model (free & private).

## 🧠 How It Works (RAG in action)

1. **Ingestion**: Your PDF is split into chunks, each converted to a vector (embedding) and stored in FAISS.
2. **Retrieval**: When you ask a question, it's converted to a vector and the most relevant chunks are found.
3. **Generation**: Those chunks + your question are sent to Llama 3, which answers **only** from the provided context.

## 🚀 Quick Start (5 minutes)

### Prerequisites
- Python 3.9 or later
- A free [Groq API key](https://console.groq.com) (sign up → API Keys)

1. **Clone the repo**  
   `git clone https://github.com/shihjen/Document_QA_ChatBot.git && cd Document_QA_ChatBot`
   `cd Document_QA_ChatBot`

2. **Create virtual environment**  
   - Windows: `python -m venv venv` → `venv\Scripts\activate`  
   - Mac/Linux: `python3 -m venv venv` → `source venv/bin/activate`

3. **Install dependencies**  
   `pip install streamlit langchain langchain-community langchain-groq langchain-text-splitters langchain-classic pypdf faiss-cpu sentence-transformers python-dotenv`

4. **Add your Groq API key**  
   Create a file named `.env` with: `GROQ_API_KEY=your_key_here` (no quotes, no spaces)

5. **Run the app**  
   `streamlit run app.py`

### 📁 Project File Structure
Document_QA_ChatBot/
├── app.py                 # Main application
├── .env                   # API key (ignored by git)
├── requirements.txt       # Dependencies
└── README.md              # This file

