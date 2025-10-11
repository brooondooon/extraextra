# Technology Stack

## Agentic Architecture Overview

```
┌─────────────────────────────────────────────────────────┐
│              Podcast Generation Pipeline                 │
│                                                           │
│  ┌──────────────┐    ┌──────────────┐    ┌────────────┐ │
│  │  Curation    │───>│   Script     │───>│   Voice    │ │
│  │   Agent      │    │   Agent      │    │ Synthesis  │ │
│  └──────────────┘    └──────────────┘    └────────────┘ │
│         │                    │                   │        │
│    [NewsAPI +           [GPT-4 with          [OpenAI     │
│     Claude 3.5]         chain-of-thought]      TTS]      │
│         │                    │                   │        │
│         v                    v                   v        │
│  ┌──────────────────────────────────────────────────┐   │
│  │        User Preference Layer (Supabase)          │   │
│  │   Historical patterns, saved articles, topics     │   │
│  └──────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────┘
```

### Pipeline Components

**Curation Agent** (Claude 3.5)
- Analyzes user preferences and article relevance
- Scores content by freshness, source authority, topic match
- Filters based on user's topics-to-avoid settings
- Makes autonomous article selection decisions

**Script Agent** (GPT-4)
- Multi-step reasoning for narrative construction
- Synthesizes information across multiple articles
- Chain-of-thought prompting for coherent podcast flow
- Context-aware transitions between topics

**Voice Synthesis** (OpenAI TTS)
- Converts script to natural-sounding audio
- SSML-based prosody control for emphasis
- User-selected voice personality applied consistently

**Memory Layer** (Supabase + Redis)
- Stores user interaction history (completed episodes, skips)
- Caches article embeddings for fast retrieval
- Tracks listening patterns for adaptive recommendations

---

## Frontend & Mobile

**Next.js 15**
- Server Components for initial page loads
- Client Components for interactive features
- API routes for backend logic
- TypeScript for type safety

**React 18**
- Context API for global state (auth, audio player)
- useState/useReducer for local state
- Custom hooks for reusable logic

**TailwindCSS + Radix UI**
- Utility-first CSS framework
- Accessible UI primitives

**Capacitor 6** (iOS)
- WebView-based native app
- Native plugins:
  - App lifecycle
  - Haptics
  - Push notifications
  - RevenueCat payments
  - Apple Sign In

---

## Backend & Database

**Supabase**
- PostgreSQL with Row-Level Security
- JWT-based authentication
- Real-time subscriptions
- User preferences stored as JSONB

**Upstash Redis**
- Article content caching (15-min TTL)
- Agent state persistence during pipeline
- Rate limiting
- Session management

---

## AI Orchestration

**LangChain Integration**
- Chains for multi-step article processing
- Prompt templates for consistent agent behavior
- Output parsers for structured responses
- Tool calling for NewsAPI integration

**Agent Workflow**
1. User triggers generation with mode selection
2. Curation Agent fetches and scores articles
3. Script Agent creates narrative with reasoning steps
4. Quality checks ensure source attribution
5. Voice synthesis completes pipeline

---

## Content & Audio

**NewsAPI**
- Real-time article fetching (100+ publishers)
- Category-based filtering
- Sorted by relevance and recency

**Mozilla Readability**
- Extracts clean article content
- Removes ads and boilerplate

**OpenAI GPT-4**
- Script generation with chain-of-thought
- Cross-article synthesis
- Context preservation

**Anthropic Claude 3.5**
- Content safety screening
- Article categorization
- Publisher detection

**OpenAI TTS**
- 44.1kHz mp3 output
- Six voice personalities
- SSML for natural prosody

---

## Payments & Subscriptions

**RevenueCat**
- Cross-platform IAP management
- Server-side receipt validation
- Webhook-based status updates
- Purchase restoration

---

## Infrastructure

**Vercel**
- Next.js optimized hosting
- Edge Functions (global CDN)
- Automatic deployments
- Environment management

**GitHub Actions**
- CI/CD pipeline
- Automated linting
- Type checking
- Production builds

---

## Security

**Authentication**
- JWT with HTTP-only cookies
- OAuth 2.0 (Google, Apple, Spotify)
- Row-Level Security in Supabase

**Data Protection**
- AES-256 encryption at rest
- TLS 1.3 in transit
- Input validation with Zod schemas

**API Security**
- Redis-based rate limiting
- CSRF protection
- SQL injection prevention

---

## Agentic Design Patterns

**Multi-Agent Pipeline**
- Specialized agents for curation, scripting, QA
- Each agent operates autonomously with clear objectives
- Sequential execution with state passing

**Chain-of-Thought Reasoning**
- GPT-4 uses explicit reasoning steps for script quality
- Intermediate outputs guide next agent decisions

**Adaptive Behavior**
- System learns from user skip patterns
- Adjusts article selection based on completion rates
- Mode routing (Bread & Butter vs Deep Dive) based on usage

**Memory & Context**
- User preference vectors stored in Supabase
- Redis caches recent article embeddings
- Historical data influences future curation

---

**Last Updated**: January 2025
