# 🚀 FinAI: Autonomous Financial Intelligence Platform

Demo Video : https://drive.google.com/file/d/1wfllt3l_5gg4HHvfiOJ3UwxQdg-ivbxw/view?usp=sharing

![Python](https://img.shields.io/badge/python-3.10+-blue.svg)
![TypeScript](https://img.shields.io/badge/typescript-5.0+-blue.svg)
![LangGraph](https://img.shields.io/badge/LangGraph-Agentic-orange)
![RAG](https://img.shields.io/badge/RAG-ChromaDB-green)

**FinAI** is a cutting-edge, local-first financial intelligence system designed to democratize institutional-grade market analysis. By leveraging a multi-agent architecture, FinAI filters noise, analyzes sentiment, and models complex second-order effects in real-time.

Unlike traditional dashboards that simply display data, FinAI employs **autonomous agents** to read, reason, and react to global financial events, offering capabilities previously reserved for top-tier hedge funds.

---

## 🌟 Key Features & "Moonshot" Modules

FinAI integrates advanced "Moonshot" modules that push the boundaries of retail financial analytics:

### 🕵️‍♂️ Forensic Agent (Anomaly Detection)
*   **Real-time Scanning**: Continuously monitors market data for statistical anomalies and irregularities.
*   **Deep Dive Analysis**: Automatically triggers a sub-agent investigation when unusual volume or price action is detected.

### 🦋 Butterfly Effect Engine (Causal Graph)
*   **Second-Order Effects**: Models complex causal chains (e.g., "Drought in Brazil" -> "Coffee Futures Spike" -> "Starbucks Margin Compression").
*   **Graph Analytics**: Uses directed graphs to visualize and predict how a single event ripples through the global economy.

### 🧬 Darwinian Breeder (Strategy Evolution)
*   **Genetic Algorithms**: Evolving trading strategies using principles of natural selection.
*   **Survival of the Fittest**: Automatically backtests thousands of strategy variations, keeping only the most robust performers.

### 🌌 Multiverse Simulator (Counterfactuals)
*   **"What If" Scenarios**: Runs Monte Carlo simulations to test portfolios against hypothetical historical divergences.
*   **Stress Testing**: Evaluates how your holdings would perform during a 2008-style crash or a 1999-style melt-up.

### 🗣️ Fed Whisperer (Audio Analysis)
*   **Tone Detection**: Uses `openai-whisper` and `librosa` to analyze the *audio* of Federal Reserve announcements, detecting subtle hawkish or dovish cues in speech patterns and tonality.
*   **Sentiment Scoring**: Quantifies the emotional weight of central bank communications.

### 🧠 Local RAG (Retrieval-Augmented Generation)
*   **Privacy-First**: Runs entirely on your local machine using **ChromaDB** and **Hugging Face Transformers**.
*   **Smart Search**: Chat with the market using natural language. The system retrieves relevant news snippets to answer complex queries without hallucinations.

---

## 🛠️ Technical Architecture

FinAI is built on a modern, modular stack designed for performance and extensibility.

### Backend (Python)
*   **Framework**: FastAPI (High-performance async API)
*   **Orchestration**: **LangGraph** (Cyclic stateful multi-agent workflows)
*   **AI/ML**: PyTorch, Transformers, Sentence-Transformers, Scikit-learn
*   **Vector Store**: ChromaDB (Local persistence for RAG)
*   **Audio Processing**: OpenAI Whisper, Librosa
*   **Scheduling**: APScheduler for periodic agent tasks

### Frontend (TypeScript)
*   **Framework**: React 18 (Vite)
*   **Styling**: Tailwind CSS (Custom "FinAI" design system with glassmorphism)
*   **State Management**: React Hooks & Context
*   **Visualization**: Recharts (Interactive financial charting)
*   **Icons**: Lucide React

---

## ⚡ Getting Started

Follow these instructions to set up the FinAI environment locally.

### Prerequisites
*   **Python 3.10+**
*   **Node.js 18+**
*   **Git**

### 1. Backend Setup

```bash
# Navigate to the backend directory
cd finai-lite/backend

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate

# Install dependencies
# This includes torch, transformers, langgraph, fastapi, etc.
pip install -r requirements.txt

# Run the Agent Server
# The server initializes local RAG models on startup (first run may take a few minutes)
uvicorn app.main:app --reload
```
*Backend API will be available at `http://localhost:8000`*

### 2. Frontend Setup

```bash
# Open a new terminal and navigate to the frontend directory
cd finai-lite/frontend

# Install Node dependencies
npm install

# Start the Development Server
npm run dev
```
*Frontend Dashboard will be available at `http://localhost:5173`*

---

## 📂 Project Structure

```
finai-lite/
├── backend/
│   ├── app/
│   │   ├── agents/         # LangGraph nodes (Trader, Forensic, Macro)
│   │   ├── services/       # Core Logic (Butterfly Effect, Breeder, RAG)
│   │   ├── api/            # FastAPI Routes & Endpoints
│   │   └── core/           # Config, Database, & Utilities
│   ├── chroma_db/          # Local Vector Database Storage
│   └── requirements.txt    # Python Dependencies
├── frontend/
│   ├── src/
│   │   ├── components/     # Reusable UI Components
│   │   ├── pages/          # Application Views (Insights, Simulator, etc.)
│   │   └── lib/            # API Clients & Utilities
│   └── package.json        # Frontend Dependencies
└── README.md               # Project Documentation
```

---

## 🔮 Roadmap

*   **Social Sentiment Integration**: Real-time scraping of Twitter/X and Reddit (WallStreetBets) to gauge retail sentiment.
*   **Live Broker Connection**: API integrations with Alpaca or Interactive Brokers for paper trading.
*   **LLM Fine-tuning**: Tools to fine-tune small local models (like Llama 3) on financial datasets.

---

## 🤝 Contributing

We welcome contributions! Whether it's fixing bugs, adding new "Moonshot" modules, or improving the UI, please feel free to fork the repository and submit a Pull Request.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request


