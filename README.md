# Ai-Avatar-Chatbot-
🤖 KARS AI – Real-Time AI Avatar Chatbot

An emotionally expressive, real-time 3D avatar chatbot powered by a local LLM (Ollama), with voice + text interaction, lip-sync, and a privacy-first design.

B.Tech CSE (AI & DS) Project · PVPIT, Budhgaon · 2025–2026

<p align="center"> <img src="images/voice-interaction.png" alt="KARS AI interface with chat panel and 3D avatar" width="850"> </p>
📌 Overview

Traditional text chatbots lack the emotional and visual richness of human conversation. Existing avatar systems often suffer from high latency, poor expressiveness, and heavy dependence on cloud AI (raising privacy concerns).

KARS AI solves this by combining:

🧠 Local LLM inference via Ollama (no cloud API cost, better privacy)
🧍 Real-time 3D avatar with lip-sync, facial expressions and gestures
🎙️ Voice + text input with spoken responses (STT / TTS)
⚡ WebSocket communication for low-latency, bidirectional messaging
✨ Features
Real-time 3D avatar (Three.js + React Three Fiber, .glb models) with a 2D avatar option
Lip-sync driven by TTS audio, plus emotion-based expressions and hand gestures
Avatar states: Idle, Listening, Talking, Explaining
Voice interaction using the browser Web Speech / Web Audio APIs
Therapy Mode – empathetic conversation templates
AI Schedule Planner – 24-slot planner with reminders/notifications
Multiple local models – switch between Llama 3, Mistral, Phi-3, etc.
Avatar customization and persistent chat history
Secure authentication with Supabase (JWT, Row Level Security)
Split-panel UI – avatar on one side, chat bubbles on the other
🏗️ System Architecture

The system follows a client–server design with four main parts:

Layer	Technology	Role
Frontend	React 18, Vite, Three.js, React Three Fiber	Chat UI, avatar rendering, voice I/O, planner
Backend	Python, FastAPI, Uvicorn	REST API, WebSocket manager, mode router, orchestration
AI Engine	Ollama (Llama 3, Mistral, Phi-3, Code Llama)	Local LLM inference and expression mapping
Data	Supabase (PostgreSQL, Auth, Realtime)	Authentication, chat history, user preferences
High-level diagram
WebSocket + REST
ollama.chat
Supabase client
Backend · FastAPI
WebSocket Manager
OllamaService
Mode RouterChat · Therapy
Frontend · React 18 + Vite
Chat Interface
Voice I/OSTT · TTS
3D AvatarThree.js / R3F
👤 UserVoice / Text
OllamaLocal LLM
SupabaseAuth · DB · Realtime
Detailed system architecture
<p align="center"> <img src="images/system-architecture.png" alt="Detailed system architecture block diagram" width="700"> </p>
Request flow
Supabase
Ollama (Local LLM)
FastAPI Backend
Frontend (React)
Supabase
Ollama (Local LLM)
FastAPI Backend
Frontend (React)
User
Speak or type a message
Speech-to-Text (Web Speech API)
Send message over WebSocket
Prompt (chat or therapy mode)
Response text + avatar state / emotion
Text + behavioral instructions
Save chat history
Text-to-Speech, lip-sync, gestures
Animated avatar speaks + chat bubble
User
Input-to-output processing flowchart
<p align="center"> <img src="images/flowchart.png" alt="KARS AI input to output processing flowchart" width="900"> </p>
Avatar behavioral states
User starts speaking /typing
LLM response ready
Long / detailed answer
Speech finished
Speech finished
Input cancelled
Idle
Listening
Talking
Explaining

State transitions take under 200 ms on average.

🛠️ Tech Stack
Frontend: React.js 18+, Vite 4+, Three.js (r150+), React Three Fiber, CSS3, Web Audio API, Web Speech API
Backend: Python 3.9+, FastAPI, Uvicorn, WebSockets, Pydantic
AI: Ollama (local LLM runtime)
Database/Auth: Supabase
Tools: VS Code, Git
🖼️ Screenshots
System initialization	Voice / chat interaction
<img src="images/ui-initialization.png" alt="Initial interface" width="420">	<img src="images/voice-interaction.png" alt="Chat with avatar" width="420">
Interface on startup, avatar idle	User question with AI response and avatar waveform
<p align="center"> <img src="images/avatar-animation.png" alt="Real-time avatar animation with gesture" width="600"><br> <em>Real-time avatar animation (gesture while speaking)</em> </p>
📊 Results
Metric	Result
Avg. AI response generation	~2.8 s
WebSocket communication delay	< 950 ms
Lip-sync accuracy	~95%
Gesture synchronization	98%
Avatar state transitions	< 200 ms
Rendering	60 FPS (720p – 4K)
Voice recognition accuracy (quiet room)	94%
TTS quality rating	8.2 / 10
Therapy Mode emotion detection	82%
Data persistence success rate	99.7%
Concurrent users tested	up to 25
User satisfaction	8.3 / 10
Users who said the avatar improved conversation	89%

Based on a user study with 30 participants.

💻 Requirements

Software: Node.js, Python 3.9+, Ollama, a Supabase project, Chrome or Firefox (WebGL-enabled)

Hardware (recommended):

CPU: Intel Core i5 / Ryzen 5 or Apple Silicon
RAM: 8 GB minimum, 16 GB recommended
GPU: 8 GB VRAM (e.g. RTX 3060/4060) for smooth local inference + rendering
Storage: SSD recommended
Microphone + speakers/headphones
Internet connection (for Supabase and external APIs)
🚀 Getting Started

⚠️ Adjust folder names and commands below to match your repository structure.

bash
# 1. Clone the repository
git clone https://github.com/<your-username>/Ai-Avatar-Chatbot-.git
cd Ai-Avatar-Chatbot-

# 2. Install and run a local model with Ollama
ollama pull llama3
ollama serve

# 3. Start the backend
cd backend
pip install -r requirements.txt
uvicorn main:app --reload

# 4. Start the frontend
cd ../frontend
npm install
npm run dev

Create a .env file with your Supabase credentials:

env
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key

Then open the local URL shown by Vite (usually http://localhost:5173).

📁 Repository Contents
File	Description
AI-AVATAR CHATBOT REPORT.pdf	Full project report
AI-Avatar-Chatbot-Building-the-Future-of-AI-Companions.pptx	Project presentation
Ai_avatar_chatbot.mp4	Demo video
images/	Screenshots and diagrams used in this README
⚠️ Limitations
~3.2 s model loading time at startup
Some users (~8%) reported an uncanny valley effect with highly realistic expressions
High-detail avatars can impact performance on lower-end devices
Requires a modern browser and at least ~1 Mbps bandwidth
Supabase cloud storage means not all data stays local (12% of users raised voice-privacy concerns)
🔮 Future Scope
Advanced emotion recognition and deeper emotional intelligence
Adaptive user interfaces
AR/VR, gaming and education-focused deployments
Hybrid local + cloud LLM setups that preserve privacy
Extended agentic features (reminders, summarization, external APIs such as weather and news)
📚 References

Key related work includes research on LLM-based avatar chatbots (Yamazaki et al., 2023), AI conversational avatars (Aliyev et al., 2025), empathetic multimodal chatbots (Xavier & John, 2024), and Ollama/Llama 3 assistants (Gohil et al., 2025). See the full list in the project report.
