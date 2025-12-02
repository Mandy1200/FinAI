# 🚀 FinAI: Autonomous Financial Intelligence Platform

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.10+-blue.svg)
![TypeScript](https://img.shields.io/badge/typescript-5.0+-blue.svg)
![LangGraph](https://img.shields.io/badge/LangGraph-Agentic-orange)
![RAG](https://img.shields.io/badge/RAG-ChromaDB-green)

**FinAI** is a next-generation, local-first financial intelligence system that uses a multi-agent architecture to filter noise, analyze sentiment, and predict market impacts in real-time. Unlike traditional dashboards, FinAI employs **autonomous agents** to read, reason, and react to global financial events.

---

## 🧠 Core Architecture & Technologies

This project showcases advanced implementations of **Agentic AI**, **RAG**, and **NLP**.

### 1. Agentic Workflow with [LangGraph](https://github.com/langchain-ai/langgraph)
FinAI moves beyond simple linear chains. It uses a **cyclic state graph** to orchestrate specialized agents.
*   **State Management**: A shared `AgentState` tracks news items, deduplication flags, extracted entities, and sentiment scores across the graph.
*   **Conditional Routing**: The graph dynamically decides the next step (e.g., if a news item is a duplicate, it skips to the end; otherwise, it proceeds to entity extraction).
*   **Nodes**:
    *   `dedup`: Checks for redundant news using fuzzy matching.
    *   `entity`: Extracts tickers (e.g., $AAPL, $TSLA) and organizations.
    *   `impact`: Analyzes sentiment and assigns a "Market Impact Score" (0-100).
    *   `trader`: Simulates trade decisions based on aggregated signals.

### 2. Local RAG (Retrieval-Augmented Generation)
A fully local, privacy-preserving RAG pipeline that allows users to "chat" with the market.
*   **Vector Database**: **ChromaDB** stores news embeddings locally.
*   **Embeddings**: Uses `sentence-transformers/all-MiniLM-L6-v2` for high-speed, dense vector representations of financial news.
*   **LLM**: Integrates `google/flan-t5-base` (via Hugging Face Transformers) for on-device answer generation without API costs.
*   **Pipeline**:
    1.  **Ingest**: News is chunked, embedded, and indexed in real-time.
    2.  **Retrieve**: User queries are embedded to find the top-k most relevant news snippets.
    3.  **Generate**: The LLM synthesizes an answer based *only* on the retrieved context, reducing hallucinations.

### 3. Advanced NLP & Forensics
*   **Sentiment Analysis**: Uses transformer-based models to detect subtle shifts in market tone.
*   **Fed Whisperer (Audio)**: *[In Development]* Uses `openai-whisper` and `librosa` to transcribe and analyze audio from Federal Reserve announcements for hawkish/dovish signals.
*   **Causal Graph**: Models second-order effects (e.g., "Oil price spike" -> "Airline stocks drop").

---

## 🛠️ Tech Stack

### Backend (Python)
*   **Framework**: FastAPI (High-performance async API)
*   **Orchestration**: LangChain & LangGraph
*   **ML/AI**: PyTorch, Transformers, Sentence-Transformers, Scikit-learn
*   **Database**: ChromaDB (Vector), SQLite (Relational)
*   **Scheduling**: APScheduler

### Frontend (TypeScript)
*   **Framework**: React (Vite)
*   **Styling**: Tailwind CSS (Dark mode, Glassmorphism)
*   **Visualization**: Recharts (Interactive financial charts), Lucide React
*   **State**: React Hooks

---

## ⚡ Quick Start

### Prerequisites
*   Python 3.10+
*   Node.js 18+

### 1. Backend Setup
```bash
cd finai-lite/backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies (including torch, transformers, langgraph)
pip install -r requirements.txt

# Run the Agent Server
uvicorn app.main:app --reload
```
*The server will start at `http://localhost:8000` and initialize the local RAG models (first run may take a minute).*

### 2. Frontend Setup
```bash
cd finai-lite/frontend

# Install dependencies
npm install

# Start the UI
npm run dev
```
*Access the dashboard at `http://localhost:5173`.*

---

## 📂 Project Structure

```
finai-lite/
├── backend/
│   ├── app/
│   │   ├── agents/         # LangGraph nodes & workflow definitions
│   │   ├── services/       # RAG, FedWhisperer, Market Data services
│   │   ├── api/            # FastAPI routes
│   │   └── core/           # Database & Config
│   ├── chroma_db/          # Local vector store persistence
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/     # React components (Charts, Feeds)
│   │   ├── pages/          # Main views (Dashboard, Simulator, Forensic)
│   │   └── lib/            # API clients
└── README.md
```

## 🔮 Roadmap

*   **Multiverse Simulator**: Monte Carlo simulations for portfolio stress testing.
*   **Darwinian Breeder**: Genetic algorithms to evolve trading strategies over time.
*   **Social Sentiment**: Integration with Twitter/X and Reddit APIs.

---

## 🤝 Contributing

Contributions are welcome! Please read `DOCUMENTATION.md` for detailed architectural guidelines.

## 📄 License

MIT License
