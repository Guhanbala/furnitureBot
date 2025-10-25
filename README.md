# Furnishing Voice AI Assistant

> A voice-enabled chatbot for furnishing shop owners with real-time voice interactions and business insights.

## Overview

The Furnishing Voice AI Assistant is a sophisticated voice-to-voice chatbot system designed specifically for furnishing shop owners. It provides seamless integration through website widgets, Facebook, and WhatsApp entry points. The system handles queries about curtains, blinds, wallpaper, upholstery, flooring, and more while maintaining strict domain focus.

## Key Features

- 🎙️ Voice-to-Voice Interaction
- 🔒 Domain-Locked Responses
- 🏪 Shop-Specific Knowledge Integration
- 🖼️ Curtain Visualizer Integration
- 📱 Automatic WhatsApp Summaries
- ⚡ Low Latency (< 2.5s turn time)
- 🚀 Flexible Deployment Options

## System Architecture

### Frontend Components
- WebRTC/MediaStream for audio handling
- Push-to-talk or Voice Activity Detection
- Text captions display
- Product/fabric swatch visualization

### Voice Gateway
- ASR: Whisper (self-hosted/cloud)
- TTS: Coqui-TTS/Piper or cloud TTS
- Streaming: Half-duplex with PCM 16 kHz mono

### Core Components
- Session Management
- Intent Classification
- Tool Routing
- RAG System
- Guardrails
- Summary Generation

### Deployment Options

#### Standalone/On-Prem
- LLM: Llama-3.1-8B-Instruct
- ASR: Whisper-medium/int8
- TTS: Coqui-XTTS/Piper
- Vector DB: Qdrant/pgvector

#### Hybrid
- Local ASR/TTS
- Cloud-hosted LLM
- Optimized for quick deployment

## Integration

### Website Integration
```html
<script src="https://cdn.hit.ai/voicebot.js"></script>
<div id="hit-voicebot" data-shop="your_shop_id"></div>
<script>
  HITVoiceBot.mount({
    shopId: "your_shop_id",
    accent: "en-IN",
    vad: true,
    captions: true
  });
</script>
```

### API Endpoints

- Session Creation: `POST /v1/sessions`
- Voice Streaming: `WebRTC wss://bot.hi-tech.ai/rtc/:sessionId`
- Text Query: `POST /v1/query`
- Summary Webhook: `POST /hooks/summary`

## Features

### Knowledge Integration
- Shop profiles
- Working hours
- Delivery areas
- Product catalogs
- Price lists
- Brand information
- FAQs

### Smart Calculators
- Wallpaper roll calculator
- Curtain material estimator
- Rod length calculator

### Visualizer Integration
- Room visualization
- Fabric preview
- Style customization

### Business Tools
- Lead capture
- Conversation summaries
- WhatsApp integration
- Analytics dashboard

## Security & Compliance

- HTTPS endpoints
- Signed media URLs
- CORS restrictions
- PII handling with consent
- Configurable data retention
- WhatsApp opt-out support

## Supported Languages

- English (Indian)
- Tamil
- Expandable to other languages

## Requirements

### System Requirements
- Node.js >= 18.x
- PostgreSQL >= 14
- Redis >= 6.2
- GPU for local LLM (if using standalone deployment)

### API Keys & Credentials
- Visualizer API access
- WhatsApp Business API credentials
- Cloud LLM API keys (if using hybrid deployment)

## Setup

1. Clone the repository
2. Install dependencies
3. Configure environment variables
4. Set up database schemas
5. Initialize vector store
6. Deploy voice models
7. Start the service