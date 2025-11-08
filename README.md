# 🤖 Voice-Powered Knowledge Graph Orchestrator

### 🎙️ Combine n8n, InfraNodus, and ElevenLabs to create a voice-enabled AI that *thinks in knowledge graphs*!

This workflow connects **ElevenLabs Conversational AI**, **n8n AI Agent**, and **InfraNodus GraphRAG** into a seamless pipeline that lets users *talk to their knowledge graphs* using natural voice input. 🧠💬

---

## 🚀 How It Works

1. 🎧 **User speaks a question** using the ElevenLabs conversational interface.
2. 📡 ElevenLabs sends the prompt (and sessionID) to an **n8n Webhook** via a POST request.
3. 🧩 The **n8n AI Agent Node** receives the request and analyzes which *expert* (knowledge graph) is best suited to answer.
4. 🔍 The AI Agent reformulates the query (if needed) and sends it to the corresponding **InfraNodus GraphRAG** endpoint.
5. 🕸️ Each **InfraNodus expert** (graph) responds with:
   - A context-aware answer  
   - A list of relevant statements (from RAG + GraphRAG)
6. 🧠 The n8n Agent integrates all responses into a single, coherent final answer.
7. 🔁 The final answer is sent back to the **n8n Webhook**.
8. 🗣️ **ElevenLabs AI** picks up the response, condenses it for conversational tone, and transforms it into speech!

---

## 🧠 Architecture Overview

🎙️ User (Voice)
↓
🧠 ElevenLabs Conversational Agent
↓
📩 n8n Webhook → 🧩 AI Agent Node → 🔗 InfraNodus Expert Graphs (GraphRAG)
↓
🧠 AI Agent (Final Integration)
↓
📬 Webhook Response
↓
🔊 ElevenLabs (Voice Output)

yaml
Copy code

---

## ⚙️ Setup Instructions

### 1. 🕸️ InfraNodus Setup
- Create an account: [https://infranodus.com](https://infranodus.com)
- Get your **API key**: [https://infranodus.com/api-access](https://infranodus.com/api-access)
- Create a separate **knowledge graph** for each “expert” (using PDFs, text, or web content).
- In n8n, paste each graph’s name into the body `name` field of its **InfraNodus HTTP Node**.
- Keep other settings as is or check [InfraNodus Access Points](https://infranodus.com/api-access) for advanced options.

### 2. 🤖 n8n Setup
- Import the provided workflow template.
- Add your **InfraNodus API key** (Bearer authorization).
- Insert your **OpenAI (or other LLM)** API key into the **LLM Node**.
- Configure the **AI Agent Node** to manage your experts.
- Add a **Webhook Node** for communication with ElevenLabs.

### 3. 🗣️ ElevenLabs Setup
- Create an ElevenLabs account: [https://elevenlabs.io](https://elevenlabs.io)
- Set up a **Conversational AI Agent**.
- Connect it to your **n8n Webhook** via the `knowledge_base` tool.
- Configure polling for webhook responses.
- The agent will handle:
  - Query forwarding 📨
  - Response retrieval 🔄
  - Voice synthesis 🎧

---

## 💬 Optional: Text + Voice Chatbot Combo

Want users to choose between text and voice?  
Check out [popupchat.dev](https://popupchat.dev) — an open-source website chat widget that can connect to your workflow and offer both modes of interaction. 💬🔊

---

## 🧰 Requirements

| Component | Purpose | Link |
|------------|----------|------|
| 🕸️ InfraNodus | GraphRAG experts / knowledge graphs | [infranodus.com](https://infranodus.com) |
| 🧠 OpenAI (or other LLM) | AI reasoning / language processing | [openai.com](https://openai.com) |
| 🎙️ ElevenLabs | Conversational AI + voice synthesis | [elevenlabs.io](https://elevenlabs.io) |
| 🧩 n8n | Orchestration and automation | [n8n.io](https://n8n.io) |

---

## 🌟 Features

✅ Multi-expert orchestration (AI decides best tool per query)  
✅ Voice-to-graph interaction via ElevenLabs  
✅ GraphRAG context-aware responses  
✅ Memory support via session IDs  
✅ Expandable with more experts or modalities  

---

## 🧭 Example Use Cases

- 🧑‍🏫 Voice-based tutoring systems with expert knowledge bases  
- 🗂️ Intelligent research assistants connecting multiple domains  
- 🎧 Interactive podcasts or exhibitions where AI explains topics dynamically  
- 💼 Corporate knowledge assistants integrated with document graphs  

---

## 🧑‍💻 Credits

Built with ❤️ using:
- **n8n** for orchestration  
- **InfraNodus GraphRAG** for structured reasoning  
- **ElevenLabs** for conversational voice AI  
- **OpenAI / LLMs** for language understanding  

---

> 💡 *“Talk to your knowledge — let graphs do the thinking, and AI do the talking.”* 🎙️🧠




