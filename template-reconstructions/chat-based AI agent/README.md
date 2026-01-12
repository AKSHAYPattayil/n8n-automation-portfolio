# 🤖 AI Agent Chatbot (n8n)

This repository contains an **AI-powered chatbot agent built using n8n**, showcasing how modern AI agents can be designed using **LLMs, memory, and tool-based reasoning**.

The workflow exposes a public chat interface where users can interact with an AI agent that intelligently decides when to respond directly and when to invoke external tools such as weather APIs or news feeds.

This project is intended for **learning and experimentation**.

---

## ✨ What This Workflow Does

- Provides a **chat-based AI agent** using n8n’s Chat Trigger
- Uses a **large language model (LLM)** for reasoning and responses
- Maintains **short-term conversational memory**
- Dynamically selects and calls **external tools**
- Returns a single, clean response back to the user

### Example interactions
- “What’s the weather in Tokyo today?”
- “Give me the latest tech news”
- “What are today’s top headlines?”

The agent determines *when* a tool is required and *which* tool best fits the user’s request.

---

Note: The chatbot’s tone has been intentionally set to be sarcastic and slightly insulting for demonstration purposes. Responses may come across as cheeky or mean.

---
## 🔧 Workflow Components

### 1. Chat Trigger
- Creates a public chat interface
- Accepts user input
- Displays the agent’s final response

---

### 2. LangChain Agent
- Core reasoning and decision-making component
- Interprets user intent
- Chooses tools when necessary
- Formats the final output

The agent behavior is primarily controlled through a **system message** that defines:
- Role and tone
- Tool-usage rules
- Response constraints

---

### 3. Language Model
- Uses Google Gemini (or any supported LLM)
- Handles reasoning, tool selection, and response generation
- Model can be swapped without changing agent logic

> API credentials are **not stored** in the workflow JSON.

---

### 4. Memory Buffer
- Stores the last few messages (short-term memory)
- Allows the agent to maintain conversational context
- Prevents excessive token usage

---

### 5. Weather Tool (HTTP Request)
- Uses the public **Open-Meteo API**
- No authentication required
- The agent dynamically fills parameters such as location and units
- Ideal for demos and public-facing agents

---

### 6. News Tool (RSS Feed Reader)
- Fetches data from public RSS feeds
- Allows the agent to retrieve real-world news
- No API keys or credentials required

---

## 🚀 How to Use

### 1. Import the Workflow
- Download the workflow JSON
- Import it into your n8n instance

---

### 2. Configure the Language Model
- Open the Language Model node
- Add your own API credentials (Gemini or another provider)
- Save the node

---

### 3. Open the Chat
- Click **“Open chat”** on the Chat Trigger node
- Start interacting with the agent

---

### 4. Experiment
Try:
- Tool-based questions (weather, news)
- Follow-up questions to test memory
- General conversation without tool usage

---

## 🔐 Security Notes

- ✅ No API keys are hardcoded
- ✅ All external services used are public
- ✅ Credentials are managed via n8n’s credential system
- ⚠️ The chat interface is public — avoid attaching sensitive tools

---

## 🎯 Use Cases

- Learning how AI agents work in n8n
- Studying tool-based reasoning patterns
- Understanding conversational memory
- Portfolio demonstration of agent architecture
- Base template for specialized agents

---

## 🛠 Possible Extensions

- Add long-term memory (database-backed)
- Integrate productivity tools (Notion, Google Sheets, etc.)
- Specialize the agent for a specific domain
- Convert the agent into a private/internal tool

---

## 📌 Attribution

This workflow was inspired by an official n8n template created by **Lucas Peyrin**.

The goal of this project was to study and reconstruct an AI agent architecture, understand how system prompts, tools, and memory interact, and adapt the workflow for learning and portfolio use.
