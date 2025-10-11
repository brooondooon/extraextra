# Technology Stack

## Architecture Overview

```
┌─────────────────────────────────────────────┐
│         Mobile App (iOS)                    │
│    Next.js 15 + React 18 + Capacitor       │
└────────────────┬────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────┐
│         API Layer (Next.js)                 │
│   /api/generate  /api/library  /api/auth   │
└────────────────┬────────────────────────────┘
                 │
        ┌────────┴────────┐
        ▼                 ▼
┌──────────────┐    ┌──────────────┐
│   Supabase   │    │Upstash Redis │
│  (Database)  │    │   (Cache)    │
└──────┬───────┘    └──────────────┘
       │
       ▼
┌─────────────────────────────────────────────┐
│         AI Processing Pipeline              │
│  NewsAPI → GPT-4 → OpenAI TTS → Audio      │
└─────────────────────────────────────────────┘
       │
       ▼
┌─────────────────────────────────────────────┐
│         External Services                   │
│  RevenueCat │ Vercel │ NewsAPI             │
└─────────────────────────────────────────────┘
```

---

## Frontend & Mobile

**Next.js 15**
- App Router with Server Components
- Built-in API routes
- TypeScript 5.0 for type safety

**React 18**
- Context API for global state (auth, player)
- Hooks for component state management

**TailwindCSS + Radix UI**
- Utility-first styling
- Accessible UI primitives

**Capacitor 6** (iOS)
- WebView-based mobile app
- Native plugins:
  - App lifecycle management
  - Haptics feedback
  - Push notifications
  - RevenueCat payments
  - Apple Sign In

---

## Backend & Database

**Supabase**
- PostgreSQL database
- Built-in authentication (JWT)
- Row-Level Security (RLS) for data isolation
- Real-time subscriptions via WebSockets

**Upstash Redis**
- Article content caching
- Session state management
- Rate limiting
- Generation progress tracking

---

## AI & Audio

**OpenAI GPT-4**
- Script generation from articles
- Article summarization
- Content synthesis across stories

**Anthropic Claude 3.5**
- Content safety screening
- Article categorization
- Publisher detection

**OpenAI TTS**
- Natural voice synthesis
- Professional-quality mp3 output (44.1kHz)
- SSML markup for prosody control

---

## Content Aggregation

**NewsAPI**
- Real-time article fetching from 100+ publishers
- Category-based organization

**Mozilla Readability**
- Clean content extraction
- Removes ads and navigation

---

## Payments

**RevenueCat**
- Cross-platform subscription management (iOS/Android)
- Server-side receipt validation
- Purchase restoration
- Subscription status webhooks

---

## Infrastructure

**Vercel**
- Next.js hosting
- Edge Functions for global CDN
- Automatic HTTPS
- Environment variable management

**GitHub Actions**
- Automated deployments
- Linting and type checking

---

## Security

**Authentication**
- JWT tokens with HTTP-only cookies
- OAuth 2.0 for social logins
- Row-Level Security in Supabase

**Data Protection**
- Encrypted at rest (AES-256)
- TLS 1.3 in transit

**API Security**
- Rate limiting via Redis
- Input validation with Zod
- CSRF protection

---

**Last Updated**: January 2025
