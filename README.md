<div align="center">

<img src="logo.png" alt="ExtraExtra Logo" width="120">

# ExtraExtra

### News podcasts generated from sources you trust, on the topics you want to hear.

Stop reading clickbait and waiting for mid podcast episodes. Start getting good news wherever you go with ExtraExtra, a personalized news podcaster in a mobile app that generates informative, engaging news podcasts on the spot, tailored exactly to your interests.

**[Visit Website](https://extraextra.live)** • **[Download on App Store](https://apps.apple.com/us/app/extraextra-news/id6749835220)** • **[View Features](FEATURES.md)**

![iOS](https://img.shields.io/badge/iOS-14%2B-blue) ![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue) ![Next.js](https://img.shields.io/badge/Next.js-15-black) ![License](https://img.shields.io/badge/License-Proprietary-red)

</div>

---

## Key Problem

News consumption is broken. Most people want to stay informed, but:

- Reading dozens of articles takes too much time
- You only trust news from certain sources
- News is riddled with clickbait and popups
- News podcast episodes release on a cadence and can be low-quality

People already listen to podcasts while commuting, exercising, and doing chores. What if your daily news could be a podcast—personalized, on-demand, and narrated in a tone you enjoy?

---

## The Solution

ExtraExtra transforms the way you consume news by synthesizing articles from the sources you trust, providing intelligent curation, detailed analysis, and professional narration. Think of it as your personal news anchor, who's constantly digging for the best news for you.

---

## Demo Video

See ExtraExtra in action:

<div align="center">

https://github.com/user-attachments/assets/07dd8870-97b2-4fdc-86d8-1a7d4bcddbe9

</div>

---

## Key Features

### **AI-Powered Content Pipeline**
- **Intelligent Summarization**: Agent dives deep into each article and extracts key info
- **Narrative Construction**: Creates high-quality, conversational podcast scripts
- **Cross-Article Synthesis**: Connects related stories for deeper understanding
- **Source Attribution**: Maintains journalistic integrity by citing publishers in your Library

### **Distinct Voice Personalities**
Premium voices from OpenAI's TTS models:
- **Female**: Doe (Basic), Ms. Frizzle (energetic), Valley Girl (casual)
- **Male**: John (Basic), Mr. Ello Gov'na (British, sophisticated), City Cowboy (GenZ slang and cowboy sayings)

Each voice has unique prosody, pacing, and personality to match your listening preference.

### **100+ Premium Publishers**
Curate from top-tier sources across 7 categories:
- **World**: NYT, Washington Post, The Guardian, BBC, Reuters, AP
- **Business**: WSJ, Financial Times, Bloomberg, The Economist, Forbes
- **Technology**: TechCrunch, The Verge, Wired, Ars Technica
- **Sports**: ESPN, The Athletic, Sports Illustrated, Bleacher Report
- **Politics**: Politico, The Hill, Roll Call, Axios
- **Entertainment**: Variety, Rolling Stone, Billboard
- **Social**: Reddit, Hacker News, Twitter trends

### **Three Listening Modes**
Optimized for different information needs:

**Bread & Butter** (Default)
- Key takeaways from top headlines
- Get a high level recap from your personalized interests and sources
- Perfect for daily catch-up

**Deep Dive**
- Thoughtful analysis with additional context
- Become an expert quickly on your interests
- Connects related stories for deeper understanding

**Hot Topics**
- Trending conversations and viral stories
- Great for catching up to prepare for water cooler conversations

### **Polished Mobile Experience**
Native iOS app built with Capacitor:
- **Home**: On-demand podcast generation and mode selection
- **Library**: See articles used and access full source content
- **Backstage**: View and replay all saved episodes (Pro/Max only)
- **Settings**: Deep personalization controls and subscription options

---

## How It Works

### **News Podcaster Agent Pipeline**

```
News Sources → Content Extraction → AI Processing → Audio Generation → Delivery
```

1. **Content Aggregation**
   - Real-time article fetching with NewsAPI
   - Content extraction using Mozilla Readability

2. **Intelligent Curation**
   - User preference matching (publishers, topics, interests)
   - Topic avoidance filtering
   - Freshness scoring (prioritize recent articles)
   - Diversity balancing across categories

3. **Script Generation**
   - Article synthesis with context preservation
   - Narrative arc construction for podcast flow
   - Transition scripting between topics
   - Source citation integration

4. **Voice Synthesis**
   - SSML markup for natural prosody
   - Emphasis and pacing controls
   - Professional-quality 44.1kHz mp3 audio

5. **Audio Assembly**
   - Segment stitching with smooth transitions
   - Native playback with iOS
   - Segmented duration bar for easy audio searching

---

## Subscription Tiers

| Feature | Free | Pro | Max |
|---------|------|-----|-----|
| **Podcast Duration Max** | 5 minutes | 10 minutes | 20 minutes |
| **Monthly Listening Limit** | 30 minutes | 100 minutes | 250 minutes |
| **Backstage Access** | ❌ | ✅ | ✅ |
| **Priority Queue** | ❌ | ❌ | ✅ (< 10s) |
| **Price** | **Free** | **$9.99/mo** | **$19.99/mo** |

[View Detailed Pricing →](SUBSCRIPTION.md)

---

## Technology Stack

**Frontend & Mobile**
- Next.js 15
- React 18
- TypeScript 5.0
- TailwindCSS
- Capacitor (iOS native)

**Backend & Database**
- Supabase (PostgreSQL, Auth, Realtime)
- Upstash Redis (Edge caching)

**AI & Audio**
- OpenAI GPT-4 (Script generation)
- Anthropic Claude 3.5 (Content analysis)
- OpenAI TTS (Voice synthesis)

**Infrastructure**
- Vercel (Hosting)
- NewsAPI (Content aggregation)
- RevenueCat (Subscription management)

[View Full Architecture →](TECH_STACK.md)

---

## Getting Started

### **Download the App**

<a href="YOUR_APP_STORE_LINK">
  <img src="https://developer.apple.com/assets/elements/badges/download-on-the-app-store.svg" alt="Download on App Store" height="50">
</a>

### **Quick Start**

1. **Sign Up** (30 seconds)
   - Email/password or social login (Google, Apple, Spotify)

2. **Choose Publishers and Topics**
   - Select 5-10 sources across categories
   - Set interests and topics to avoid

3. **Pick Your Voice**
   - Listen to 6 samples
   - Choose the one that fits your style

4. **Generate First Podcast**
   - Hit "Create Podcast"
   - Start listening when the push notification comes in!

---

## Privacy & Data

### **What We Collect**
- Email address (authentication)
- Publisher preferences (curation)
- Usage analytics (improvement)
- Subscription status (billing)

[Read Full Privacy Policy →](PRIVACY.md)

---

## Platform Roadmap

- ✅ **iOS** (Live) - Native app with full feature set
- **Android** (Q4 2025) - Google Play release
- **Web Player** (Q4 2025) - Listen on desktop

---

## Support & Feedback

We're here to help:
- **Website**: extraextra.live
- **Email**: brandonqin@berkeley.edu
- **App Issues**: Use the App Store "Report a Problem" feature
- **Feature Requests**: We read every email!

---

## About the Creator

**Brandon Qin** - Product Manager

**Why I Built This**: I hated reading news with all the clickbait, popups, and blockers. Started hating waiting for my favorite news podcast just for a mid episode drop. So i built an app so I could listen to news podcasts on what I wanted to hear, whenever. Hope you love it as much as I do for your commutes and coffee breaks!

**Connect**
- **Website**: extraextra.live
- **GitHub**: @brooondooon
- **LinkedIn**: linkedin.com/brandonqin
- **Twitter/X**: x.com/extraextralive

---

## Legal

**Source Code**: Proprietary. This repository contains documentation only.

**Content Licensing**: All news content remains the intellectual property of respective publishers. ExtraExtra provides aggregation, transformation, and delivery services only.

**Publisher Relationships**: ExtraExtra operates under fair use principles and maintains relationships with publishers for attribution and licensing compliance.

**Trademarks**: Publisher names, logos, and marks are trademarks of their respective owners.

[Terms of Service](TERMS.md) • [Privacy Policy](PRIVACY.md)

---

## Show Your Support

If ExtraExtra helps you stay informed:
- Star this repository
- Leave an App Store review
- Share on social media
- Tell a friend who's always "too busy to read"

---

<div align="center">

**ExtraExtra**

*News podcasts from sources you trust, on the topics you want to hear.*

[extraextra.live](https://extraextra.live) • [Download Now](#) • [Features](FEATURES.md) • [Tech Stack](TECH_STACK.md)

---

**Documentation Last Updated**: January 2025
**Current Version**: 1.0 (iOS)

</div>
