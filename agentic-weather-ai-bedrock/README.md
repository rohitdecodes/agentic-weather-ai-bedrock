# 🚀 Agentic Weather AI  
### Built with Amazon Bedrock + Claude 4.5 Sonnet

An end-to-end **Agentic AI system** that dynamically plans, executes, and processes real-world API calls to deliver live weather forecasts.

This project demonstrates how Large Language Models can function as reasoning agents — not just text generators.

---

## 🧠 What Makes This “Agentic”?

Traditional AI systems:

Input → Hardcoded API → Output

This system:

Input → AI Planning → API Execution → AI Processing → Response

Instead of hardcoding API endpoints, the AI:

- Understands natural language location input  
- Determines geographic coordinates  
- Dynamically generates National Weather Service API calls  
- Executes real HTTP requests  
- Extracts structured forecast data  
- Converts raw JSON into human-friendly summaries  

---

## 🏗 System Architecture

### Step-by-step Flow

1. **User Input**
   - City name (Seattle)
   - ZIP code (90210)
   - Location description ("Largest city in California")

2. **AI Planning (Claude 4.5 Sonnet)**
   - Determines approximate latitude & longitude  
   - Generates NWS Points API URL  

3. **Points API Call**
   - Returns forecast office & grid information  

4. **Forecast API Call**
   - Fetches real-time weather forecast JSON  

5. **AI Processing**
   - Converts raw structured data into readable summary  

6. **Final Output**
   - Practical, human-friendly weather forecast  

---

## ⚙️ Tech Stack

- Amazon Bedrock (LLM orchestration)
- Claude 4.5 Sonnet (Reasoning + Planning + Summarization)
- boto3 (AWS SDK for Python)
- National Weather Service API (Live weather data)
- Streamlit (Web interface)
- Pure Python (No heavy AI frameworks)

---

## 📂 Project Structure

agentic-weather-ai-bedrock/

│  
├── cli.py                  # Command-line agent  
├── weather_agent_web.py    # Streamlit web application  
├── requirements.txt  
├── README.md  
└── architecture.png        # (Optional system diagram)  

---

## 🖥 Installation & Setup

### 1️⃣ Clone Repository

git clone https://github.com/TheOGRohit/agentic-weather-ai-bedrock.git  
cd agentic-weather-ai-bedrock  

---

### 2️⃣ Install Dependencies

pip install -r requirements.txt  

---

### 3️⃣ Configure AWS Credentials

Make sure AWS CLI is configured:

aws configure  

Use:

Region: us-west-2  

Your IAM user must have access to Amazon Bedrock runtime.

---

## ▶️ Run the Application

### CLI Version

python cli.py  

---

### Web Version (Recommended)

streamlit run weather_agent_web.py  

Then open the local Streamlit URL in your browser.

---


## 🎯 Key Learnings

- Designing Agentic AI workflows  
- Using LLMs as planners vs summarizers  
- Dynamic API orchestration  
- Prompt engineering for structured outputs  
- Handling multi-step AI-driven systems  
- Building CLI + Web UI for the same core agent  

---

## 🚀 Future Improvements

- Replace curl with requests library  
- Add caching layer  
- Implement retry & timeout strategies  
- Add structured logging  
- Deploy on AWS (EC2 / ECS / Lambda)  
- Extend to multi-tool agent system  

---

## ⚠️ Disclaimer

This project uses official National Weather Service data for educational purposes.  
For critical weather decisions, always consult official government sources.

---

## 👨‍💻 Author

Rohit Patil  
B.Tech Student | AI & Systems Enthusiast  
Graduating 2028  

---

# 🌟 Why This Project Matters

This project demonstrates that LLMs can:

- Plan multi-step workflows  
- Interact with external APIs  
- Process structured data  
- Adapt to flexible user input  

It moves beyond chatbot-style AI into real-world autonomous system design.