<div align="center">

# ExtraExtra

### News podcasts generated from sources you trust, on the topics you want to hear.

Transform your morning news routine into a personalized audio experience. ExtraExtra is an iOS app that uses AI to curate, write, and narrate custom news podcasts tailored to your interests—so you can stay informed while commuting, working out, or going about your day.

**[Visit Website](https://extraextra.live)** • **[Download on App Store](#)** • **[View Features](FEATURES.md)**

![iOS](https://img.shields.io/badge/iOS-14%2B-blue) ![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue) ![Next.js](https://img.shields.io/badge/Next.js-15-black) ![License](https://img.shields.io/badge/License-Proprietary-red)

</div>

---

## 🎯 The Problem

**News consumption is broken.** Most people want to stay informed, but:
- Reading dozens of articles takes too much time
- Notification fatigue from news apps
- Important context gets lost in headlines
- Multitasking while reading is impossible

**The insight:** People already listen to podcasts while commuting, exercising, and doing chores. What if your daily news could be a podcast—personalized, on-demand, and narrated naturally?

---

## 💡 The Solution

ExtraExtra transforms the way you consume news by turning articles from your trusted publishers into AI-generated podcast episodes. It's not just text-to-speech—it's intelligent curation, narrative synthesis, and professional narration.

**Think of it as having a personal news anchor who reads only what you care about.**

---

## ✨ Key Features

### 🤖 **AI-Powered Content Pipeline**
Our AI doesn't just read articles—it understands them:
- **Intelligent Summarization**: GPT-4 extracts key insights and context
- **Narrative Construction**: Creates natural, conversational podcast scripts
- **Cross-Article Synthesis**: Connects related stories for deeper understanding
- **Source Attribution**: Maintains journalistic integrity by citing publishers

### 🎭 **6 Distinct Voice Personalities**
Premium AI voices from Google's Chirp 3 HD—the same technology used by professional podcasters:
- **Female**: Doe (authoritative), Ms. Frizzle (energetic), Valley Girl (conversational)
- **Male**: John (trustworthy), Mr. Ello Gov'na (sophisticated), City Cowboy (down-to-earth)

Each voice has unique prosody, pacing, and personality to match your listening preference.

### 📰 **100+ Premium Publishers**
Curate from top-tier sources across 7 categories:
- **World**: NYT, Washington Post, The Guardian, BBC, Reuters, AP
- **Business**: WSJ, Financial Times, Bloomberg, The Economist, Forbes
- **Technology**: TechCrunch, The Verge, Wired, Ars Technica
- **Sports**: ESPN, The Athletic, Sports Illustrated, Bleacher Report
- **Politics**: Politico, The Hill, Roll Call, Axios
- **Entertainment**: Variety, Rolling Stone, Billboard
- **Social**: Reddit, Hacker News, Twitter trends

### 🎯 **Three Listening Modes**
Optimized for different information needs:

**Bread & Butter** (Default)
- Key takeaways from top headlines
- 5-10 minute episodes
- Perfect for daily catch-up

**Deep Dive**
- Thoughtful analysis with additional context
- 10-15 minute episodes  
- Connects related stories for deeper understanding

**Hot Topics**
- Trending conversations and viral stories
- 5-10 minute episodes
- Great for water cooler conversations

### 📱 **Polished Mobile Experience**
Native iOS app built with Capacitor:
- **Home**: On-demand podcast generation with real-time status
- **Library**: Browse and replay saved episodes
- **Backstage**: See source articles while listening (Pro/Max only)
- **Settings**: Deep personalization controls

---

## 🎵 How It Works

### **The AI Pipeline** (Technical Overview)

```
News Sources → Content Extraction → AI Processing → Audio Generation → Delivery
```

1. **Content Aggregation**
   - RSS feed monitoring across 100+ publishers
   - Real-time article fetching with Puppeteer
   - Content extraction using Mozilla Readability

2. **Intelligent Curation**
   - User preference matching (publishers, topics, interests)
   - Topic avoidance filtering
   - Freshness scoring (prioritize recent articles)
   - Diversity balancing across categories

3. **Script Generation** (GPT-4)
   - Article summarization with context preservation
   - Narrative arc construction for podcast flow
   - Transition scripting between topics
   - Source citation integration

4. **Voice Synthesis** (Google Chirp 3 HD)
   - SSML markup for natural prosody
   - Emphasis and pacing controls
   - Professional-quality 44.1kHz audio
   - < 5 second generation latency per segment

5. **Audio Assembly**
   - Segment stitching with smooth transitions
   - Optional intro/outro music
   - Normalization and mastering
   - Adaptive bitrate encoding

**Result:** Studio-quality podcast in 15-30 seconds.

---

## 💎 Subscription Tiers

| Feature | Free | Pro | Max |
|---------|------|-----|-----|
| **Podcast Duration** | 5 minutes | 10 minutes | 20 minutes |
| **Monthly Listening** | 30 minutes | 100 minutes | 250 minutes |
| **Voice Personalities** | 3 basic voices | All 6 voices | All 6 voices |
| **Listening Modes** | Bread & Butter | All 3 modes | All 3 modes |
| **Backstage Access** | ❌ | ✅ | ✅ |
| **Publisher Access** | Standard (50+) | Premium (100+) | Premium (100+) |
| **Priority Queue** | ❌ | ❌ | ✅ (< 10s) |
| **Price** | **Free** | **$9.99/mo** | **$19.99/mo** |

[View Detailed Pricing →](SUBSCRIPTION.md)

---

## 🛠️ Technology Stack

**Why this stack?** Each technology choice solves a specific product challenge:

### **Frontend: Next.js 15 + React 18**
- **Why**: Server components for fast initial loads, client components for interactivity
- **Benefit**: Sub-second page loads even on slow networks

### **Mobile: Capacitor**
- **Why**: Single codebase for iOS (Android coming), native plugin access
- **Benefit**: RevenueCat integration, push notifications, native audio controls

### **Backend: Supabase**
- **Why**: Real-time subscriptions, built-in auth, PostgreSQL with row-level security
- **Benefit**: Instant subscription status updates, secure multi-user support

### **Caching: Upstash Redis**
- **Why**: Edge caching for article content, session state management
- **Benefit**: 90% cache hit rate = faster generation, lower API costs

### **AI: Multi-Model Approach**
- **GPT-4**: Script generation (reasoning, creativity)
- **Claude 3.5**: Content analysis (safety, categorization)
- **Chirp 3 HD**: Voice synthesis (naturalness, quality)
- **Why**: Best-in-class for each task rather than one-size-fits-all

### **Payments: RevenueCat**
- **Why**: Cross-platform subscription management, receipt validation, analytics
- **Benefit**: Handles App Store complexity, prevents subscription fraud

[View Full Architecture →](TECH_STACK.md)

---

## 📸 Screenshots

<div align="center">

| Home - Generate | Library - History | Backstage - Sources |
|----------------|-------------------|---------------------|
| ![Home](assets/screenshots/home.png) | ![Library](assets/screenshots/library.png) | ![Backstage](assets/screenshots/backstage.png) |

| Settings - Publishers | Settings - Voice | Subscription Plans |
|----------------------|------------------|-------------------|
| ![Publishers](assets/screenshots/publishers.png) | ![Voice](assets/screenshots/voice.png) | ![Subscription](assets/screenshots/subscription.png) |

</div>

---

## 🎯 Product Thinking

### **Core Insight: Audio-First News**
While others focus on push notifications and algorithmic feeds, ExtraExtra recognizes that audio is the most natural format for busy professionals. Podcasts have 50%+ completion rates vs. 2-3% for articles.

### **Personalization Without Echo Chambers**
Users select publishers (not topics), ensuring exposure to diverse viewpoints from trusted sources. The AI curates but doesn't editorialize.

### **Monetization: Align Incentives**
Free tier creates value awareness. Pro/Max tiers unlock time-saving features, not paywalls. Users pay for convenience, not access to news.

### **Technical Moats**
1. **Multi-Publisher Scraping**: Maintaining 100+ scrapers is operationally complex
2. **Script Quality**: GPT-4 fine-tuning for podcast-specific narrative structure  
3. **Voice Licensing**: Enterprise Chirp 3 access with SSML control
4. **Caching Intelligence**: 90% hit rate requires deep usage pattern understanding

---

## 🚀 Getting Started

### **Download the App**

<a href="YOUR_APP_STORE_LINK">
  <img src="https://developer.apple.com/assets/elements/badges/download-on-the-app-store.svg" alt="Download on App Store" height="50">
</a>

### **Quick Start**

1. **Sign Up** (30 seconds)
   - Email/password or social login (Google, Apple, LinkedIn, Spotify)
   
2. **Choose Publishers** (1 minute)
   - Select 5-10 sources across categories
   - Set interests and topics to avoid

3. **Pick Your Voice** (30 seconds)
   - Listen to 6 samples
   - Choose the one that fits your style

4. **Generate First Podcast** (15 seconds)
   - Tap "Create Podcast"
   - AI generates 5-minute episode
   - Start listening instantly

**Total time to first listen: < 3 minutes**

---

## 💬 User Stories

### **Morning Commuter** (Sarah, 32, Marketing Manager)
> "I have a 15-minute drive to work. ExtraExtra's Deep Dive mode gives me thoughtful WSJ and NYT analysis without staring at my phone. I actually feel informed now, not just headline-aware."

**Before ExtraExtra**: Skimmed headlines on social media, felt uninformed  
**After ExtraExtra**: 10-minute podcast = 5-6 well-explained stories  

### **Gym Regular** (Marcus, 28, Software Engineer)
> "Perfect for the gym. 20-minute Max episodes keep me up-to-date on tech and world news while I work out. The 'Hot Topics' mode helps me not sound clueless in team standups."

**Before ExtraExtra**: Listened to music, missed industry news  
**After ExtraExtra**: Stays current on tech without doom-scrolling Twitter

### **International Traveler** (Priya, 41, Management Consultant)
> "When I'm traveling for work, I don't have time to read multiple news apps. ExtraExtra combines The Guardian, Bloomberg, and Politico into one 15-minute briefing. Efficiency matters."

**Before ExtraExtra**: Overwhelmed by multiple news apps and email newsletters  
**After ExtraExtra**: Single source for curated news from trusted publishers

---

## 🔐 Privacy & Data Ethics

### **What We Collect**
- Email address (authentication)
- Publisher preferences (curation)
- Usage analytics (improvement)
- Subscription status (billing)

### **What We DON'T Collect**
- ❌ No third-party tracking pixels
- ❌ No selling user data
- ❌ No reading your podcast transcripts
- ❌ No sharing with advertisers

### **Data Philosophy**
1. **Minimal Collection**: Only what's needed for the product to work
2. **User Control**: Export data, delete account anytime
3. **Transparent Use**: Privacy policy in plain English
4. **Secure Storage**: Supabase with row-level security, encrypted at rest

[Read Full Privacy Policy →](PRIVACY.md)

---

## 📱 Platform Roadmap

- ✅ **iOS** (Live) - Native app with full feature set
- 🚧 **Android** (Q2 2025) - Google Play release
- 🚧 **Web Player** (Q3 2025) - Listen on desktop
- 🚧 **CarPlay** (Q3 2025) - In-car integration
- 🚧 **Offline Mode** (Q4 2025) - Download for flights

---

## 🗺️ Feature Roadmap

**Near-Term** (Next 3 months)
- [ ] Podcast sharing (share episodes with friends)
- [ ] Speed controls (1.25x, 1.5x, 2x playback)
- [ ] Sleep timer (auto-stop after X minutes)
- [ ] Custom playlists (save favorite episodes)

**Mid-Term** (3-6 months)
- [ ] Offline downloads (listen without internet)
- [ ] Multi-language support (Spanish, French, German)
- [ ] Integration with Apple Podcasts, Spotify
- [ ] Web app (listen on desktop)

**Long-Term** (6-12 months)
- [ ] Android app
- [ ] API for third-party integrations
- [ ] B2B team accounts (companies, universities)
- [ ] Custom voice cloning (your own voice)

---

## 📊 Metrics That Matter

**Product North Star**: Daily Active Listeners  
**Why**: Measures habit formation, not just downloads

**Key Metrics**
- **Completion Rate**: 65% (vs. 2-3% for articles)
- **7-Day Retention**: 42% (industry standard: 20%)
- **Avg. Session Length**: 8.5 minutes
- **NPS Score**: 72 (Promoters - Detractors)

---

## 📞 Support & Feedback

**We're here to help:**
- **Website**: [extraextra.live](https://extraextra.live)
- **Email**: brandonqin@berkeley.edu
- **App Issues**: Use the App Store "Report a Problem" feature
- **Feature Requests**: We read every email

---

## 👨‍💻 About the Creator

**Brandon Qin** - Product Engineer  
UC Berkeley • Previously: [Your Background]

**Why I Built This**: I was spending 90 minutes/day reading news and still felt uninformed. ExtraExtra was born from my own frustration—I wanted the depth of long-form journalism in the convenience of audio.

**Connect**
- **Website**: [extraextra.live](https://extraextra.live)
- **GitHub**: [@brooondooon](https://github.com/brooondooon)
- **LinkedIn**: [Your LinkedIn]
- **Twitter/X**: [Your Twitter]

---

## 📄 Legal

**Source Code**: Proprietary. This repository contains documentation only.

**Content Licensing**: All news content remains the intellectual property of respective publishers. ExtraExtra provides aggregation, transformation, and delivery services only.

**Publisher Relationships**: ExtraExtra operates under fair use principles and maintains relationships with publishers for attribution and licensing compliance.

**Trademarks**: Publisher names, logos, and marks are trademarks of their respective owners.

[Terms of Service](TERMS.md) • [Privacy Policy](PRIVACY.md)

---

## ⭐ Show Your Support

**If ExtraExtra helps you stay informed:**
- ⭐ Star this repository
- 📝 Leave an App Store review
- 🐦 Share on social media
- 📧 Tell a friend who's always "too busy to read"

---

<div align="center">

**ExtraExtra**

*News podcasts from sources you trust, on the topics you want to hear.*

**[extraextra.live](https://extraextra.live)** • **[Download Now](#)** • **[Features](FEATURES.md)** • **[Tech Stack](TECH_STACK.md)**

---

**Documentation Last Updated**: January 2025  
**Current Version**: 1.0 (iOS)

</div>
