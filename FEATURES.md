# Features

## AI-Powered Podcast Generation

ExtraExtra uses a three-stage pipeline to create news podcasts:

1. **Content Aggregation**
   - Fetches articles from your selected publishers via NewsAPI
   - Extracts clean content using Mozilla Readability

2. **Script Generation**
   - GPT-4 reads full articles and creates conversational podcast scripts
   - Connects related stories for narrative flow
   - Maintains source attribution for all content

3. **Voice Synthesis**
   - OpenAI TTS generates audio with natural prosody
   - Professional-quality 44.1kHz mp3 output
   - SSML markup for emphasis and pacing control

---

## Voice Personalities

Six distinct voices to match your listening preference:

**Female Voices**
- **Doe**: Professional, authoritative (Basic voice)
- **Ms. Frizzle**: Energetic, engaging
- **Valley Girl**: Conversational, casual

**Male Voices**
- **John**: Trustworthy, steady (Basic voice)
- **Mr. Ello Gov'na**: British, sophisticated
- **City Cowboy**: GenZ slang and cowboy sayings

Choose your preferred voice in Settings. It applies to all generated podcasts.

---

## Publisher Selection

100+ news sources across 7 categories:

- **World**: NYT, Washington Post, The Guardian, BBC, Reuters, AP
- **Business**: WSJ, Financial Times, Bloomberg, The Economist, Forbes
- **Technology**: TechCrunch, The Verge, Wired, Ars Technica
- **Sports**: ESPN, The Athletic, Sports Illustrated, Bleacher Report
- **Politics**: Politico, The Hill, Roll Call, Axios
- **Entertainment**: Variety, Rolling Stone, Billboard
- **Social**: Reddit, Hacker News, Twitter trends

You select which publishers to follow. The AI curates from your choices only.

---

## Listening Modes

### Bread & Butter (Default)
- Key takeaways from top headlines
- High-level recap of your interests
- Perfect for daily catch-up

### Deep Dive
- Detailed analysis with additional context
- Connects related stories for deeper understanding
- Become an expert quickly on your interests

### Hot Topics
- Trending conversations and viral stories
- Great for water cooler talk preparation

---

## Mobile App

### Home
- One-tap podcast generation
- Select listening mode
- Real-time generation status
- Start listening when ready

### Library
- View all previously generated podcasts
- Save source articles for later reading
- Delete old episodes

### Backstage (Pro/Max Only)
- Browse and replay saved episodes
- See which articles were used
- Access full source content

### Settings
- Choose your voice
- Select publishers and topics
- Set interests and topics to avoid
- Manage subscription and account

---

## Authentication

Supported login methods:
- Email/password
- Google OAuth
- Apple Sign In
- Spotify

Powered by Supabase Auth with row-level security.

---

## Subscription Management

RevenueCat handles:
- Cross-platform subscription management
- Receipt validation
- Purchase restoration across devices
- Real-time subscription status updates

Billing is monthly through Apple App Store or Google Play Store.

---

**Last Updated**: January 2025
