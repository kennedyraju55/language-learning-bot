# 🌍 Language Learning Bot

![Python 3.11+](https://img.shields.io/badge/Python-3.11%2B-3776AB?logo=python&logoColor=white)
![License MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Local LLM](https://img.shields.io/badge/LLM-Gemma%204-FF6F00?logo=google&logoColor=white)
![Privacy First](https://img.shields.io/badge/Privacy-First-blueviolet?logo=lock&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-Powered-black?logo=ollama&logoColor=white)

**Practice conversations in 15+ languages with a patient AI tutor — vocabulary tracking, lesson plans, and pronunciation tips, all running locally with Gemma 4.**

```
+---------------------------------------------------------+
|               LANGUAGE LEARNING BOT                     |
|                                                         |
|  +----------+    +---------------+    +--------------+  |
|  | Learner   |--->|  CLI / Web UI |--->|  Tutor Core  |  |
|  | (You!)    |<---|  (Rich /      |<---|  Engine      |  |
|  +----------+    |  Streamlit)   |    +------+-------+  |
|                  +---------------+           |          |
|    Language:                                 v          |
|    Spanish,      +---------------+    +--------------+  |
|    French,       | Vocab Tracker |<-->|  Ollama API  |  |
|    Japanese...   | & Progress    |    |  (Gemma 4)   |  |
|                  | (JSON)        |    |  :11434      |  |
|  +----------+    +---------------+    +--------------+  |
|  | Level:    |          |                               |
|  | Beginner  |    +-----v-------+                       |
|  | Intermed. |    | Lesson Plan |                       |
|  | Advanced  |    | Generator   |                       |
|  +----------+    +-------------+                        |
+---------------------------------------------------------+
```

## Features

- **15+ Languages** — Spanish, French, German, Italian, Japanese, Korean, Chinese, Arabic, Hindi, and more
- **3 Proficiency Levels** — Beginner, intermediate, and advanced with adaptive responses
- **Conversational Practice** — Chat naturally and get real-time corrections with explanations
- **Grammar Lessons** — Request mini lessons on any grammar topic with examples and exercises
- **Pronunciation Tips** — Phonetic breakdowns, mouth position guidance, and English comparisons
- **Vocabulary Tracker** — Save words with translations, examples, and mastery status
- **Vocabulary Quizzes** — Auto-generated quizzes from your saved word lists
- **Lesson Plan Generator** — Structured multi-week curricula with daily activities
- **Progress Dashboard** — Track sessions, study hours, and words learned per language
- **100% Local & Private** — Your learning data stays on your machine; no cloud APIs

## Quick Start

### Prerequisites

| Requirement | Version |
|-------------|---------|
| Python      | 3.11+   |
| Ollama      | latest  |
| Gemma 4     | via Ollama |

### Install & Run

```bash
# 1. Clone the repository
git clone https://github.com/kennedyraju55/language-learning-bot.git
cd language-learning-bot

# 2. Install dependencies
pip install -r requirements.txt

# 3. Start Ollama and pull Gemma 4
ollama serve &
ollama pull gemma4

# 4a. Launch the Web UI
streamlit run src/language_learner/web_ui.py

# 4b. Or use the CLI
python -m language_learner.cli chat --language spanish --level beginner
```

### Docker

```bash
docker-compose up
# Web UI at http://localhost:8501
```

## Tech Stack

| Layer        | Technology                          |
|-------------|--------------------------------------|
| LLM          | Gemma 4 via Ollama                  |
| Backend      | Python 3.11, Click CLI              |
| Web UI       | Streamlit                           |
| API          | FastAPI / Uvicorn                   |
| Terminal UI  | Rich (panels, tables, progress)     |
| Config       | PyYAML                              |
| Testing      | pytest, pytest-cov                  |
| Containers   | Docker, Docker Compose              |

## Project Structure

```
language-learning-bot/
├── src/language_learner/
│   ├── core.py         # Tutor engine, vocab tracker, progress
│   ├── cli.py          # Click CLI with Rich output
│   ├── web_ui.py       # Streamlit web dashboard
│   ├── api.py          # FastAPI REST endpoints
│   ├── config.py       # YAML configuration loader
│   └── utils.py        # LLM client helpers & utilities
├── common/
│   └── llm_client.py   # Shared Ollama/Gemma 4 client
├── tests/
│   ├── test_core.py    # Unit tests for core logic
│   └── test_cli.py     # CLI integration tests
├── config.yaml         # Languages, levels, storage config
├── requirements.txt    # Python dependencies
├── Dockerfile          # Multi-stage Docker build
├── docker-compose.yml  # Full stack with Ollama
├── Makefile            # Dev shortcuts (install, test, run)
└── setup.py            # Package setup with entry points
```

## Author

**Nrk Raju Guthikonda**
Senior Software Engineer @ Microsoft — Copilot Search Infrastructure

- GitHub: [kennedyraju55](https://github.com/kennedyraju55)
- Dev.to: [kennedyraju55](https://dev.to/kennedyraju55)
- LinkedIn: [nrk-raju-guthikonda](https://linkedin.com/in/nrk-raju-guthikonda-504066a8/)

---

<p align="center">Built with Gemma 4 — part of a 90+ local LLM project portfolio</p>
