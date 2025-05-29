Project Structure
 agents/
 api_agent.py # Market data from yfinance
 scraper_agent.py # Web scraper for earnings calendar
 retriever_agent.py # Semantic search using FAISS
 language_agent.py # GPT-4 powered response generation
 voice_agent.py # Whisper + TTS
 orchestrator/
 main.py # Central coordination agent
 streamlit_app/
 app.py # Streamlit-based user interface
 data_ingestion/
 fetch_data.py # (Optional) Additional data ingestion
 docs/
 ai_tool_usage.md # Log of AI usage and model configurations
 Dockerfile # Container setup
 requirements.txt # Python dependencies
 README.md # Project overview and instructions
Quick Start
1. Clone the repository
 git clone https://github.com/your-username/morning-market-brief.git
 cd morning-market-brief
2. Install dependencies
 pip install -r requirements.txt
3. Start each agent service in separate terminals:
 uvicorn agents.api_agent:app --port 8000
 uvicorn agents.scraper_agent:app --port 8001
 uvicorn agents.retriever_agent:app --port 8002
 uvicorn agents.language_agent:app --port 8003
4. Run Streamlit UI
 cd streamlit_app
 streamlit run app.py
Docker Deployment
docker build -t market-assistant .
docker run -p 8004:8004 market-assistant

Features
| Agent | Description | Tech Stack |
|--------------------|---------------------------------------------|-----------------------------------|
| api_agent | Market data from Yahoo Finance | yfinance, FastAPI |
| scraper_agent | Earnings calendar scrape | BeautifulSoup, requests |
| retriever_agent | Similarity-based info search | faiss, sentence-transformers |
| language_agent | GPT-based reasoning and narration | openai, FastAPI |
| voice_agent | Voice input/output | whisper, pyttsx3 |
| orchestrator | Agent coordination and flow logic | requests, FastAPI |
| streamlit_app | User-facing interface | Streamlit |

Benchmarks
| Functionality | Response Time (avg) | Accuracy |
|---------------------------|---------------------|----------|
| Financial data fetch | ~300ms | |
| Web scraping | ~500ms | |
| Semantic retrieval | ~200ms | |
| GPT-4 generation | ~2-3s | |
| Whisper transcription | ~1-2s | |

AI Tool Usage
- Prompt examples for language_agent
- Whisper model settings (e.g., base)
- Sentence Transformer used: all-MiniLM-L6-v2
- FAISS vector index: IndexFlatL2
- GPT model: gpt-4 via OpenAI APIDeployment
Deploy the app publicly using:
- Streamlit Cloud
- Railway
- Docker on AWS/GCP
Share the deployed URL along with a screen recording
