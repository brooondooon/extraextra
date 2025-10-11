# Technology Stack & Architecture

This document provides a comprehensive overview of ExtraExtra's technical architecture, technology choices, and engineering principles.

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                        Mobile App (iOS)                      │
│              Next.js 15 + React 18 + Capacitor              │
└──────────────────┬──────────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────────────────┐
│                    API Layer (Next.js)                       │
│           /api/generate  /api/library  /api/auth            │
└──────────────────┬──────────────────────────────────────────┘
                   │
        ┌──────────┴──────────┐
        ▼                     ▼
┌───────────────┐    ┌────────────────┐
│   Supabase    │    │ Upstash Redis  │
│  (Database)   │    │   (Caching)    │
└───────┬───────┘    └────────────────┘
        │
        │ User Data, Sessions, Podcasts
        │
        ▼
┌─────────────────────────────────────────────────────────────┐
│                   AI Processing Pipeline                     │
│  ┌──────────┐  ┌──────────┐  ┌────────────┐  ┌──────────┐ │
│  │Puppeteer │→ │  GPT-4   │→ │  Chirp 3   │→ │  Audio   │ │
│  │ Scraper  │  │ Scripts  │  │   Voice    │  │ Assembly │ │
│  └──────────┘  └──────────┘  └────────────┘  └──────────┘ │
└─────────────────────────────────────────────────────────────┘
        │
        ▼
┌─────────────────────────────────────────────────────────────┐
│                  External Services                           │
│  RevenueCat  │  Firebase  │  Vercel  │  CDN                │
└─────────────────────────────────────────────────────────────┘
```

---

## 🎨 Frontend Stack

### **Next.js 15 (App Router)**
**Why Chosen**:
- Server Components reduce client-side JavaScript by 40%
- Built-in API routes eliminate need for separate backend
- Edge runtime deployment on Vercel for global CDN
- Incremental Static Regeneration for dynamic content

**Key Features Used**:
- Server Components for initial page loads
- Client Components for interactivity (audio player, forms)
- Route Groups for mobile-specific layouts
- Middleware for authentication checks

### **React 18 + TypeScript 5.0**
**Why Chosen**:
- Concurrent rendering for smoother UX
- Type safety catches bugs at compile time
- Better IDE support and autocomplete
- Self-documenting code through types

**State Management**:
- React Context for global state (auth, player)
- Local state with useState/useReducer
- No Redux (unnecessary complexity for this app)

### **TailwindCSS + Radix UI**
**Why Chosen**:
- Utility-first CSS = faster development
- Radix provides accessible primitives
- No runtime CSS-in-JS overhead
- Design system consistency

---

## 📱 Mobile Stack

### **Capacitor 6**
**Why Chosen** (vs. React Native):
- Single codebase (Next.js runs in mobile WebView)
- Access to native APIs via plugins
- Easier debugging (Chrome DevTools works)
- Smaller team = simpler stack

**Native Plugins Used**:
- @capacitor/app (App lifecycle)
- @capacitor/haptics (Touch feedback)
- @capacitor/push-notifications (Alerts)
- @revenuecat/purchases-capacitor (Payments)
- @capacitor-community/apple-sign-in (Auth)

### **iOS Specific Features**
- AVAudioSession for proper audio routing
- Background audio playback
- Lock screen media controls
- Push notification integration

---

## 🗄️ Backend Stack

### **Supabase (PostgreSQL + Auth + Realtime)**
**Why Chosen**:
- Open-source alternative to Firebase
- Full PostgreSQL (not NoSQL limitations)
- Row-Level Security (RLS) for data isolation
- Real-time subscriptions via WebSockets
- Built-in authentication

**Database Schema Highlights**:
- Users table with preferences JSONB
- Podcasts table with audio URLs
- Usage logs for tracking monthly limits
- Subscription plans configuration

**Security**:
- Row-Level Security ensures users only see their data
- JWT-based authentication
- Encrypted at rest (AES-256)

### **Upstash Redis (Edge Caching)**
**Why Chosen**:
- Serverless (pay-per-request)
- Global edge network (low latency)
- Redis compatibility (familiar API)

**Use Cases**:
- Article content caching (15-minute TTL)
- Rate limiting (prevent abuse)
- Session state management
- Podcast generation progress tracking

**Performance Impact**:
- **Cache Hit Rate**: 87%
- **Latency Reduction**: 200ms → 15ms average
- **Cost Savings**: 70% fewer GPT-4 API calls

---

## 🤖 AI/ML Stack

### **OpenAI GPT-4**
**Why Chosen**:
- Best-in-class reasoning and creativity
- Handles complex narrative construction
- Reliable JSON output mode
- Good context window (128K tokens)

**Use Cases**:
1. **Script Generation**: Converts articles into podcast scripts
2. **Article Summarization**: Extracts key points
3. **Content Synthesis**: Connects related stories

**Cost Management**:
- Cache article summaries (15min TTL)
- Use GPT-3.5 for simple tasks
- Batch processing where possible

### **Anthropic Claude 3.5 Sonnet**
**Why Chosen**:
- Better at classification and safety
- Faster than GPT-4 for structured tasks
- More affordable for high-volume operations

**Use Cases**:
1. **Content Safety**: Screens for inappropriate content
2. **Category Classification**: Organizes articles by topic
3. **Publisher Detection**: Identifies news sources

### **Google Cloud Text-to-Speech (Chirp 3 HD)**
**Why Chosen**:
- Best naturalness (vs. ElevenLabs, Amazon Polly)
- SSML support for fine control
- Stable pricing ($16/1M chars)
- 44.1kHz professional quality

**SSML Features Used**:
- `<break>` for pauses between stories
- `<emphasis>` for important words
- `<prosody>` for rate/pitch control
- `<say-as>` for numbers, dates, acronyms

---

## 💳 Payment Stack

### **RevenueCat**
**Why Chosen**:
- Abstracts Apple/Google payment complexity
- Server-side receipt validation (prevents fraud)
- Webhooks for subscription events
- Analytics and churn analysis

**Features**:
- Cross-platform subscription management
- Receipt validation
- Restore purchases functionality
- Real-time subscription status via webhooks

---

## 🌐 Infrastructure & DevOps

### **Vercel (Hosting & CDN)**
**Why Chosen**:
- Optimized for Next.js (same company)
- Edge Functions (run code globally)
- Automatic HTTPS and CDN
- Preview deployments for PRs

**Deployment**:
- Automatic deployments on git push
- Edge regions: SF and DC for US coverage
- Environment variable management
- Domain configuration

### **GitHub Actions (CI/CD)**
- Automated linting on PRs
- Type checking before deployment
- Production builds verified
- Automated deployments to Vercel

---

## 📊 Performance Metrics

| Metric | Target | Current |
|--------|--------|---------|
| **Time to First Byte** | < 200ms | 145ms |
| **Largest Contentful Paint** | < 2.5s | 1.8s |
| **First Input Delay** | < 100ms | 42ms |
| **Podcast Generation Time** | < 30s | 18-25s |
| **API Response Time (p95)** | < 500ms | 320ms |

---

## 🔐 Security Measures

1. **Authentication**
   - JWT tokens with short expiry
   - HTTP-only cookies
   - CSRF protection

2. **Data Protection**
   - Row-Level Security (RLS)
   - Encrypted at rest (AES-256)
   - TLS 1.3 in transit

3. **API Security**
   - Rate limiting
   - Input validation (Zod schemas)
   - SQL injection prevention

4. **Content Safety**
   - Claude 3.5 screens content
   - Publisher allowlist
   - SSRF protection in scraper

---

## 🚀 Scaling Strategy

**Current**: Handles ~10K daily active users

**Next Threshold (50K users)**:
- Cloudflare CDN for audio files
- Redis Cluster implementation
- Database read replicas

**100K+ users**:
- Separate API servers
- Queue-based podcast generation
- Multi-region database deployment

---

**Last Updated**: January 2025
