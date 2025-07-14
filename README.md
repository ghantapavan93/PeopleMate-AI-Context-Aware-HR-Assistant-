# 🧠 PeopleMate AI – Context-Aware HR Assistant
> **"Not just an HR chatbot — a proactive teammate that understands who you are, what you need, and why it matters."**

PeopleMate AI is a modular, production-ready HR assistant designed for the modern workplace. Built in the spirit of **Nibnab's goal-oriented, ambient agents**, it helps employees seamlessly access HR services like **PTO balance**, **onboarding**, **benefits**, **policy lookup**, and **DEI/wellness support** — without hunting through documents or forms.

---

## 🚀 Why PeopleMate?

Today’s HR systems are fragmented, reactive, and impersonal. Employees waste time navigating dashboards or pinging HR for routine queries. PeopleMate flips that model: it operates **proactively**, with **contextual awareness**, **auth-scoped responses**, and **goal-driven reasoning**.

This is **not a demo** — it’s a deployable assistant system, designed with:
- Modular **LangChain agents** for real-time interaction
- **Vector-native memory** (MiniLM + Pinecone + ChromaDB) for personalized recall
- Responsible AI logging (Langfuse + Evidently AI)
- Real-world inference APIs (FastAPI + Firebase Auth)
- Zero-shot + few-shot + CoT prompting with fallback chains

---

## 🧩 System Architecture

User Query (e.g. “What’s my PTO?”)
│
▼
[Firebase Auth + JWT Context]
│
▼
🔄 LangChain Agent Orchestration
├── 🧭 Planner Agent (intent routing)
├── 🔍 Retriever Agent (Pinecone/ChromaDB)
└── 🧠 Critic Agent (response refinement, fallback)
│
▼
🧠 Prompt Engine (Zero-shot | Few-shot | CoT)
│
▼
📊 Langfuse + Evidently (Observability, fallback logging)
│
▼
✅ Scoped, Human-like Answer (real-time via FastAPI)


---

## 🛠️ Tech Stack

| Layer               | Technologies Used                                                                 |
|--------------------|-------------------------------------------------------------------------------------|
| **LLM Agents**      | LangChain (Planner → Retriever → Critic)                                           |
| **Vector Memory**   | MiniLM embeddings + Pinecone + ChromaDB                                            |
| **Inference API**   | FastAPI backend, scoped JWT user context                                           |
| **Auth**            | Firebase Auth (user roles, session-aware responses)                                |
| **Prompting**       | Zero-shot, Few-shot, Chain-of-Thought, scoped fallbacks                            |
| **Observability**   | Langfuse (token logging, latency, fallback reasons) + Evidently AI                 |
| **Deployment**      | Dockerized FastAPI + Firebase integration; designed for EC2 / Cloud Run / Vercel   |

---

## 🌟 Key Features

- **Scoped Queries with Identity Awareness**  
  → “How many PTO days do *I* have left?” will use JWT context to pull the correct user-specific answer.

- **Real-Time Retrieval with Policy Awareness**  
  → Integrates vector search for DEI, benefits, wellness, and onboarding policy documents.

- **Agentic Delegation**  
  → Planner → Retriever → Critic chain allows dynamic reasoning, fallback handling, and intent clarification.

- **Fallback-Resilient Prompting**  
  → Zero-shot where possible, few-shot where examples exist, CoT for ambiguous reasoning.

- **Observability Built In**  
  → All requests tracked by Langfuse (token cost, latency, fallback path), making it Responsible-AI-ready.

---

## 🧠 Sample Use Cases

| User Query                                           | Agent Behavior                                                                 |
|-----------------------------------------------------|---------------------------------------------------------------------------------|
| “How much PTO do I have left?”                     | Authenticated → scoped query → fast response via embedded memory               |
| “What is the company’s parental leave policy?”      | Vector search → policy chunking → retrieval + summarization                    |
| “I’m a new hire. Where do I find onboarding tasks?” | Contextual planner agent → redirects to onboarding flow                        |
| “What DEI programs are active this month?”          | Filters vector DB based on date, DEI tag, and user role                        |

---

## 📊 Live Monitoring Snapshot

Tracked with Langfuse:
- Token cost per query
- Agent routing decisions
- Fallback trigger reasons
- Latency distribution
- Response confidence scores

---

## ✨ Vision Forward

PeopleMate is not just an HR tool — it's a **context-aware workplace companion**. Future iterations will include:
- **Slack/Microsoft Teams integration**
- **Voice-based interaction**
- **Auto-notifications for policy updates**
- **Sentiment + wellness signals for personalized nudges**

---

## 🧑‍💼 Built By

Pavankalyan Ghanta  
AI Engineer | GenAI Systems Developer  
[LinkedIn](https://www.linkedin.com/in/pavankalyan-ghanta-b20115200/) • [GitHub](https://github.com/ghantapavan93)

---

## 📂 Project Structure
peoplemate/
│
├── agents/
│ ├── planner.py
│ ├── retriever.py
│ └── critic.py
│
├── prompts/
│ ├── few_shot_examples.json
│ └── cot_fallbacks.json
│
├── api/
│ ├── main.py (FastAPI routes)
│ └── auth.py (Firebase + JWT integration)
│
├── vector_db/
│ └── pinecone_client.py
│
├── observability/
│ ├── langfuse_logger.py
│ └── evidently_integration.py
│
├── docs/
│ └── architecture_diagram.png
│
└── README.md

---

## 🛠️ Try It Locally

```bash
git clone https://github.com/ghantapavan93/PeopleMate-AI-Context-Aware-HR-Assistant.git
cd peoplemate
pip install -r requirements.txt
uvicorn api.main:app --reload

Make sure you configure .env with your:

Firebase credentials

Pinecone API key

Langfuse API key

📣 Contributions Welcome
This is an open initiative to build context-aware assistants that empower employees. Feel free to fork, raise issues, or contribute to future modules like:

Voice query support

Slack bot integration

PDF policy ingestion pipelines

💬 Final Thought
"In the age of ambient AI, assistants shouldn’t just answer questions — they should understand context, intent, and act as partners."
PeopleMate brings that vision to life for HR, wellness, and workplace empowerment.

vbnet
Copy
Edit

Let me know if you'd like a version with images (e.g., architecture diagrams), or tailored for 
