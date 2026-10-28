# Ai-Avatar-Chatbot-
🤖 KARS AI – Real-Time AI Avatar Chatbot

An emotionally expressive, real-time 3D avatar chatbot powered by a locally-run LLM for privacy, low latency and zero API cost.

B.Tech CSE (AIDS) Project · PVPIT, Budhgaon · 2025–2026

📖 Overview

Traditional text chatbots lack emotional and visual engagement, while existing avatar systems often depend on cloud AI, suffer from high latency, and have limited expressiveness. KARS AI bridges this gap by combining:

🧠 Local LLM inference (Ollama) – private, offline-capable reasoning
🧍 Real-time 3D avatar with lip-sync, facial expressions and gestures
🎙️ Multimodal interaction – voice or text input, spoken + visual output
⚡ WebSocket communication for sub-second bidirectional messaging
✨ Key Features
Real-time 3D avatar (GLB model) rendered with Three.js & React Three Fiber
Lip-sync using TTS audio analysis and facial blend shapes (visemes)
Avatar states: Listening · Talking · Explaining
Voice input (STT) and voice output (TTS) via Web Speech / Web Audio APIs
Therapy Mode – empathetic conversation templates
AI Schedule Planner – 24-slot planner with reminders
Avatar customization and 2D/3D avatar toggle
Auth & persistent chat history using Supabase
Multiple local models – Llama 3, Mistral, Phi-3 (switchable)
Auto-read toggle, chat history panel, split-panel UI
🏗️ System Architecture
Layer	Technology	Responsibility
Frontend	React 18, Vite, Three.js, React Three Fiber	Chat UI, avatar rendering, voice I/O, planner
Backend	Python, FastAPI, Uvicorn	REST APIs, WebSocket manager, mode router, Ollama service
AI Engine	Ollama (Llama 3, Mistral, Phi-3)	Local inference, expression mapping
Database	Supabase (PostgreSQL, Auth, Realtime)	JWT auth, chat history, user preferences

Processing flow: User input (voice/text) → Speech-to-Text → WebSocket → FastAPI → Ollama LLM → Response + avatar state → TTS → Lip-sync & gestures → Avatar output

🛠️ Tech Stack
Frontend: React.js 18+, Vite 4+, Three.js (r150+), React Three Fiber, CSS3, Web Audio API, Web Speech API
Backend: Python 3.9+, FastAPI, Uvicorn, WebSockets
AI: Ollama (Llama 3 8B, Mistral, Phi-3, Code Llama)
Database/Auth: Supabase
Tools: VS Code, Git, Chrome / Firefox
💻 Requirements

Software: Node.js, Python 3.9+, Ollama, a Supabase project, Chrome or Firefox (WebGL support)

Hardware (recommended):

CPU: Intel Core i5 / Ryzen 5 / Apple M-series
RAM: 8 GB minimum (16 GB recommended)
GPU: 8 GB VRAM (e.g. RTX 3060 / 4060) or Apple unified memory
Storage: SSD (512 GB NVMe tested)
Microphone + speakers/headphones
Stable internet (for Supabase and external APIs)
🚀 Getting Started

Adjust folder names and commands to match your project structure.

bash
# 1. Clone the repository
git clone https://github.com/<your-username>/Ai-Avatar-Chatbot-.git
cd Ai-Avatar-Chatbot-

# 2. Install and start Ollama, then pull a model
ollama pull llama3

# 3. Start the backend
cd backend
pip install -r requirements.txt
uvicorn main:app --reload

# 4. Start the frontend
cd frontend
npm install
npm run dev

Create a .env file with your Supabase URL and keys before running.

📊 Results
Metric	Result
Average AI response time	2.8 s
WebSocket communication delay	< 950 ms
Avatar state transition	< 200 ms
Rendering	60 FPS (720p – 4K)
Lip-sync accuracy	~95%
Gesture coordination	98%
Speech recognition accuracy (quiet room)	94%
TTS quality rating	8.2 / 10
Therapy Mode emotion detection	82%
Data persistence success rate	99.7%
Concurrent users tested	Up to 25
Overall user satisfaction	8.3 / 10
Users who said the avatar improved conversation	89%

User study: 30 participants, compared against text-based chatbots.

⚠️ Limitations
~3.2 s model loading time at startup
Uncanny-valley discomfort reported by 8% of users
Needs a modern browser and ≥ 1 Mbps connection
12% of users raised voice-data privacy concerns; Supabase cloud storage adds some exposure
High-detail avatars can be heavy on low-end devices
🔮 Future Scope
Advanced emotion recognition and emotional intelligence
Adaptive user interfaces
AR/VR, gaming and education domains
Hybrid local + cloud LLM deployments with privacy preservation
Agentic AI features: reminders, summarization, and external APIs (weather, news)
📁 Repository Contents
File	Description
AI-AVATAR CHATBOT REPORT.pdf	Full project report
AI-Avatar-Chatbot-Building-the-Future-of-AI-Companions.pptx	Project presentation
Ai_avatar_chatbot.mp4	Demo video
📚 References

Key works include Yamazaki et al. (SIGDIAL 2023), Aliyev et al. (2025), Atkare et al. (PuneCon 2025), Basit & Shafique (tinyDigiClones), Xavier & John (2024), Devi et al. (EMPATHIC, 2024) and Gohil et al. (2025). See the full report for the complete list.
