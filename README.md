# Agentic Weather AI

**Real-time weather forecasts powered by an LLM reasoning agent — built on Amazon Bedrock + Claude Sonnet.**

Unlike a traditional API wrapper, this system uses the model as a planner: it interprets flexible user input, derives coordinates, constructs National Weather Service API calls on the fly, and converts raw JSON into a readable forecast. No hardcoded endpoints, no rigid input format.

---

## How It Works

```
User Input → AI Planning → Points API → Forecast API → AI Summarization → Output
```

1. **User provides a location** — city name, ZIP code, or a natural language description (e.g. *"largest city in California"*)
2. **Claude determines coordinates** — infers latitude/longitude and constructs the NWS Points API URL
3. **Points API call** — retrieves the forecast office and grid metadata
4. **Forecast API call** — fetches live weather data from the NWS
5. **Claude summarizes** — converts structured JSON into a concise, human-readable forecast

The model acts in two distinct roles: **planner** (step 2) and **summarizer** (step 5). This separation is intentional and worth understanding.

---

## Tech Stack

| Component | Role |
|---|---|
| Amazon Bedrock | LLM API orchestration |
| Claude Sonnet | Reasoning, planning, summarization |
| boto3 | AWS SDK for Python |
| National Weather Service API | Live weather data (free, no key required) |
| Streamlit | Web interface |

No LangChain, no LlamaIndex — deliberately vanilla Python to keep the agent logic visible and understandable.

---

## Project Structure

```
agentic-weather-ai-bedrock/
├── cli.py                  # Command-line interface
├── weather_agent_web.py    # Streamlit web app
├── requirements.txt
├── README.md
└── architecture.png        # System diagram (optional)
```

---

## Setup

### 1. Clone the repo

```bash
git clone https://github.com/TheOGRohit/agentic-weather-ai-bedrock.git
cd agentic-weather-ai-bedrock
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure AWS credentials

```bash
aws configure
# Region: us-west-2
```

Your IAM user needs Bedrock runtime access (`bedrock:InvokeModel`).

---

## Running the App

**CLI:**
```bash
python cli.py
```

**Web (recommended):**
```bash
streamlit run weather_agent_web.py
```

---

## What This Actually Demonstrates

- Using an LLM as a **dynamic API planner**, not just a text generator
- Separating planning and summarization into distinct model calls
- Handling multi-step, state-dependent workflows without a framework
- Prompt engineering for structured intermediate outputs
- Building the same agent core behind both a CLI and web UI

---

## Potential Next Steps

- Swap `curl` subprocess calls for the `requests` library
- Add a caching layer to avoid redundant NWS calls
- Implement retry logic and request timeouts
- Add structured logging (currently print-based)
- Deploy to AWS (EC2 / Lambda / ECS)
- Extend to a multi-tool agent (add radar, alerts, historical data)

---

## Disclaimer

Uses official National Weather Service data. For critical weather decisions, consult [weather.gov](https://weather.gov) directly.

---

**Rohit Patil** · B.Tech  · [GitHub](https://github.com/TheOGRohit)
