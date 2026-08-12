<div align="center">

# Ajaneeshwar S

**Voice AI & Agentic Systems Engineer**

Real-time speech pipelines · Conversational agent orchestration · Telephony · LLM platforms

[![LinkedIn](https://img.shields.io/badge/LinkedIn-1A365D?style=flat-square)](https://www.linkedin.com/in/ajaneeshwar/)
[![Email](https://img.shields.io/badge/Email-1A365D?style=flat-square)](mailto:ajaneeshwar05@gmail.com)
![Location](https://img.shields.io/badge/Chennai,_India-1A365D?style=flat-square)

</div>

---

I build **voice agents that hold a real conversation** — and the unglamorous layers underneath that make them work: streaming audio transport, turn-taking, provider orchestration, telephony, evaluation and guardrails.

Most of my day is spent on latency, interruption handling and the places where a pipeline quietly breaks. Around that I ship the rest of the system too — agentic LLM backends, RAG, full-stack interfaces, and the Docker/Kubernetes infrastructure it all runs on.

Currently **Lead AI Engineer @ TheVertical.ai**, where I own production delivery and deployment across the team's AI products.

---

## The pipeline I work in

```mermaid
flowchart LR
    A["Caller<br/>PSTN · SIP · WebRTC"] --> B["Transport<br/>LiveKit · WebSocket"]
    B --> C["VAD<br/>Silero"]
    C --> D["Denoise<br/>DeepFilterNet · DSP"]
    D --> E["Streaming<br/>STT"]
    E --> F["Turn detection<br/>endpointing · barge-in"]
    F --> G["LLM<br/>tools · RAG · guardrails"]
    G --> H["Streaming<br/>TTS"]
    H --> B

    classDef stage fill:#1A365D,stroke:#0F2440,stroke-width:1px,color:#FFFFFF
    class A,B,C,D,E,F,G,H stage
```

Every stage is swappable, instrumented, and measured — because in voice the failure modes are *latency* and *turn-taking*, not accuracy.

---

## Featured open source

### 🎧 [SpectraHush](https://github.com/Ajaneeshwar/SpectraHush)
Streaming implementation of **Berouti-style modified spectral subtraction** for real-time noise reduction. Classical DSP, no model weights, no GPU — runs in the audio callback.

`Python` · `DSP` · `speech-enhancement`

### 🎙️ [DenoiseStream](https://github.com/Ajaneeshwar/DenoiseStream)
Real-time microphone noise suppression streamed over **WebSocket**, with pluggable Spectral Gate and DeepFilterNet backends behind one interface — swap the denoiser without touching the transport.

`Python` · `WebSocket` · `DeepFilterNet` · `realtime-audio`

---

## Production work

Source is private, so here's what I've actually built:

| | |
|---|---|
| **Real-time speech pipeline** | Modular STT providers behind one interface, VAD-gated denoising with live resampling, WebSocket audio streaming, and a turn-gating controller emitting partial / final / early-final / interruption events. |
| **Agent orchestration layer** | Full-duplex agents on **Pipecat** with Silero VAD, end-of-turn detection and true barge-in. Provider registries for STT / LLM / TTS / embeddings with config merge, validation, per-tenant dispatch and secret masking — any provider swaps per client with no code change. |
| **Custom telephony layer** | Inbound, outbound and warm-transfer flows over PSTN/SIP trunks and **LiveKit** rooms — WebRTC signalling, telephony webhooks, WebSocket media streams, call disposition codes, and in-call tool calling for transfer, termination and callback scheduling. |
| **Campaign dialling engine** | Event-driven outbound orchestration over Redis pub/sub — batch scheduling, stale-campaign recovery, retries, rate limiting and concurrency caps behind circuit breakers. |
| **Agent evaluation harness** | Two agents run against each other over an internal transport with *configurable simulated network latency*, recording every session so turn-taking, latency and dialogue quality are regression-tested before release. |
| **Autoprompter** | Prompt-optimisation workbench — generates prompts with guardrails, synthesises eval cases, runs GEPA rewrite search, and gates promotion behind regression checks. |
| **Voice fine-tuning** | Moved a 19-node conversation graph with per-turn RAG to per-client **LoRA adapters hot-swapped via vLLM multi-LoRA**, after tracing format hallucination and routing failure back to prompt overload. |

---

## Stack

**Voice & speech**

![Pipecat](https://img.shields.io/badge/Pipecat-1A365D?style=flat-square)
![LiveKit](https://img.shields.io/badge/LiveKit-1A365D?style=flat-square&logo=livekit&logoColor=white)
![WebRTC](https://img.shields.io/badge/WebRTC-1A365D?style=flat-square&logo=webrtc&logoColor=white)
![WebSockets](https://img.shields.io/badge/WebSockets-1A365D?style=flat-square&logo=socketdotio&logoColor=white)
![Whisper](https://img.shields.io/badge/Whisper-1A365D?style=flat-square)
![Silero VAD](https://img.shields.io/badge/Silero_VAD-1A365D?style=flat-square)
![DeepFilterNet](https://img.shields.io/badge/DeepFilterNet-1A365D?style=flat-square)

**LLM & agents**

![LangGraph](https://img.shields.io/badge/LangGraph-2C5282?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-2C5282?style=flat-square&logo=langchain&logoColor=white)
![FAISS](https://img.shields.io/badge/FAISS-2C5282?style=flat-square&logo=meta&logoColor=white)
![Unsloth](https://img.shields.io/badge/Unsloth_·_TRL-2C5282?style=flat-square)
![vLLM](https://img.shields.io/badge/vLLM-2C5282?style=flat-square)
![Langfuse](https://img.shields.io/badge/Langfuse-2C5282?style=flat-square)

**Engineering**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)

---

<details>
<summary><b>More projects</b></summary>

<br>

- **[AWS AI Agents for Business Analytics](https://github.com/Ajaneeshwar/aws-ai-agents-analytics)** — agentic system on Bedrock AgentCore for cloud cost analytics: tool orchestration over structured pricing data, LLM-driven code execution, session management and guardrails.
- **[Fuzzy LLM-RAG](https://github.com/Ajaneeshwar/Fuzzy-llm-rag-a-hybrid-approach)** — hybrid retrieval combining fuzzy matching with dense embeddings.
- **[AI Engineer Agent](https://github.com/Ajaneeshwar/ai-engineer-agent)** — autonomous coding agent experiment.
- **[NL-to-SQL Query Generation](https://github.com/Ajaneeshwar/Natural-Language-To-Sql-Query-generation-using-Gen-Ai)** — natural-language interface over SQL databases with dynamic schema detection.
- **[Flask Auth API with OTP 2FA](https://github.com/Ajaneeshwar/Flask-Authentication-API-with-OTP-based-2FA)** — production-ready auth service: JWT, email OTP, rate limiting, Bcrypt.
- **[Python Complete Bootcamp](https://github.com/Ajaneeshwar/python-complete-bootcamp)** — full Python course I wrote for freshers.
- **[Automated Text Recognition](https://github.com/Ajaneeshwar/Automated-text-recognition)** — OpenCV + Tesseract OCR over images, video and live camera.
- **[Telecom Churn Prediction](https://github.com/Ajaneeshwar/Predicting-Customer-Churn-for-Telecom-Growth)** — 93.3% AUC with XGBoost, feature engineering and social-network analysis.

</details>

---

## Writing & recognition

- 📄 **Published** — *"Automated Text Recognition from Visuals using OpenCV"*, International Conference on Applied Mathematical Techniques and Bio-Inspired Computations (ISBN 978-93-93333-67-4)
- 🎤 **Presented** — *"Natural Language to SQL Query Execution App"*, International Conference on AI & Data Science
- 👥 **Mentoring** — trained 75+ students on AI/ML and ran AI productivity and placement workshops

---

<div align="center">
<sub>Open to conversations about voice AI, real-time systems and agent infrastructure.</sub>
</div>
