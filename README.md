# EcoPulse AI 🌱

**Real-Time Environmental Intelligence System**

[![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-3178C6?logo=typescript)](https://www.typescriptlang.org/)
[![Socket.io](https://img.shields.io/badge/Socket.io-4.0-black?logo=socket.io)](https://socket.io/)
[![Supabase](https://img.shields.io/badge/Supabase-Database-3ECF8E?logo=supabase)](https://supabase.io/)

---

## 🚀 Overview

**EcoPulse AI** is a **Real-Time Environmental Intelligence System** that tracks and optimizes daily sustainability behavior using AI-driven insights.

It processes real-time environmental data (AQI, weather) along with user-generated inputs through a **simulated streaming pipeline inspired by Pathway**. The system combines AI models, event-driven architecture, and live APIs to deliver actionable recommendations for reducing carbon footprint, water usage, and plastic waste.

> "Our system continuously processes environmental data using an event-driven streaming architecture, combining real-time APIs and AI models to generate actionable sustainability insights."

---

## ✨ Features

### 🔄 Real-Time Data Streaming
- **Live AQI & Weather Data**: Continuous streaming via WebSockets (Socket.io)
- **Event-Driven Architecture**: Pathway-inspired streaming pipeline
- **3-Second Update Interval**: Real-time dashboard updates
- **Dual Data Sources**: OpenWeatherMap API + Simulated fallback

### 🤖 AI-Powered Intelligence
- **Carbon Footprint Estimation**: Rule-based + predictive hybrid model
- **Plastic Classification**: Image-based ML classification system
- **AI Chat Assistant**: Prompt-based NLP for sustainability guidance
- **Receipt Scanner**: OCR-based impact estimation from grocery bills
- **Personalized Recommendations**: Context-aware eco-tips

### 📊 Tracking & Analytics
- **Carbon Tracker**: Daily emissions logging with category breakdown
- **Environmental Dashboard**: Real-time metrics visualization
- **Trend Prediction**: AI-powered carbon trend analysis
- **Eco-Score Calculation**: Gamified sustainability scoring

### 🏆 Gamification
- **Points System**: Earn eco-points for sustainable actions
- **Leaderboards**: Community rankings and competitions
- **Badges & Certificates**: Achievements for milestones
- **Streak Tracking**: Consistency rewards

### 🗺️ Maps & Location
- **Eco Map**: Nearby recycling centers and EV stations
- **AQI Visualization**: Air quality heatmaps
- **Location-Based Insights**: Personalized recommendations

### 👥 Community
- **Go-Green Campaigns**: Community challenges and events
- **Social Features**: Connect with eco-conscious users
- **Campaign Creation**: Start your own environmental initiatives

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    EcoPulse AI Architecture                  │
└─────────────────────────────────────────────────────────────┘

┌──────────────┐         ┌──────────────┐         ┌──────────┐
│   Frontend   │◄───────►│   Backend    │◄───────►│ External │
│   (React)    │WebSocket│   (Node.js)  │   API   │   APIs   │
└──────────────┘         └──────────────┘         └──────────┘
       │                         │                      │
       ▼                         ▼                      ▼
┌──────────────┐         ┌──────────────┐         ┌──────────┐
│  Real-Time   │         │   AI Layer   │         │OpenWeathe│
│   Dashboard  │         │  (Carbon ML) │         │   rMap   │
└──────────────┘         └──────────────┘         └──────────┘
       │                         │
       ▼                         ▼
┌──────────────┐         ┌──────────────┐
│  Supabase    │         │  Streaming   │
│  (Auth/DB)   │         │   Engine     │
└──────────────┘         └──────────────┘
```

### Real-Time Streaming Pipeline

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   Sensors   │───►│   Stream    │───►│  Process    │───►│  Dashboard  │
│    & APIs   │    │   Layer     │    │   & AI      │    │   Update    │
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
                          │
                   Socket.io (3s)
                   Event-Driven
```

---

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI framework
- **TypeScript** - Type safety
- **Vite** - Build tool
- **Tailwind CSS** - Styling
- **Framer Motion** - Animations
- **Recharts** - Data visualization
- **Socket.io Client** - Real-time communication

### Backend
- **Node.js** - Runtime
- **Express** - Web framework
- **Socket.io** - WebSocket server
- **Supabase** - Database & Authentication
- **Deno Edge Functions** - Serverless AI processing

### AI & ML
- **OpenAI GPT-4o-mini** - NLP chat assistant
- **Tesseract.js** - OCR for receipt scanning
- **Custom ML Models** - Carbon estimation algorithms

### External APIs
- **OpenWeatherMap** - Weather & AQI data
- **Supabase Auth** - User authentication

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- npm or bun
- OpenWeatherMap API key (optional, for real data)

### Installation

1. **Clone the repository**
```bash
git clone <repository-url>
cd leaf-path-main
```

2. **Install dependencies**
```bash
npm install
```

3. **Set up environment variables**
```bash
# Create .env file
cp .env.example .env

# Add your API keys
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_key
OPENWEATHER_API_KEY=your_openweather_key  # Optional
```

### Running the Application

#### Option 1: Full Stack (Recommended)

**Terminal 1 - Start Backend Server:**
```bash
node backend/server.js
```
Server will start on http://localhost:3001

**Terminal 2 - Start Frontend:**
```bash
npm run dev
```
Frontend will start on http://localhost:5173

#### Option 2: Frontend Only
```bash
npm run dev
```
Note: Real-time streaming features will be unavailable

---

## 🌊 Real-Time System Explained

### How It Works

EcoPulse AI simulates a **real-time streaming pipeline** using an **event-driven architecture**:

1. **Data Sources**: 
   - Live APIs (OpenWeatherMap for AQI & weather)
   - User-generated inputs (carbon logs, activities)
   - Simulated environmental sensors (fallback)

2. **Streaming Layer** (Socket.io):
   - WebSocket connections for bidirectional communication
   - 3-second emission interval for live updates
   - Automatic reconnection handling

3. **Processing Layer**:
   - Real-time data normalization
   - AI model inference (carbon prediction)
   - Trend analysis and alerting

4. **Presentation Layer**:
   - Live dashboard updates
   - Animated metric changes
   - Color-coded indicators based on values

### Pathway-Inspired Architecture

> "We simulate real-time streaming using an event-driven architecture inspired by Pathway"

While we use Socket.io for our implementation, the architecture follows Pathway's principles:
- **Event-driven processing**: Data flows through event streams
- **Real-time transformations**: Data is processed as it arrives
- **Continuous updates**: Dashboard reflects live state changes
- **Scalable design**: Can handle multiple concurrent connections

---

## 🤖 AI System Explained

### Hybrid AI Approach

EcoPulse AI uses a **multi-model AI system**:

#### 1. Carbon Estimation Model
```typescript
// Rule-based + predictive model
const carbon = calculateCarbon({
  distance: 25,        // km traveled
  energyLevel: 'normal',
  meatMeals: 2,
  vegMeals: 1,
  waste: 'low'
});
// Returns: total emissions + category + personalized tips
```

**Emission Factors** (based on EPA/IPCC guidelines):
- Transport: 0.21 kg CO2/km
- Energy: 1-5 kg CO2 (based on usage level)
- Food: 0.5-2 kg CO2 per meal
- Waste: 1-3 kg CO2 (based on level)

#### 2. Plastic Classifier
- Image-based classification using ML
- Identifies plastic packaging types
- Provides recycling recommendations

#### 3. AI Chat Assistant
- **Prompt-based NLP** using GPT-4o-mini
- Context-aware responses using user carbon data
- Real-time sustainability advice

#### 4. Receipt Scanner
- **OCR-based extraction** using Tesseract.js
- Item recognition and categorization
- Environmental impact estimation

---

## 📁 Project Structure

```
leaf-path-main/
├── backend/                    # Real-time streaming server
│   ├── server.js              # Express + Socket.io server
│   ├── stream.js              # Data streaming logic
│   └── services/
│       └── envAPI.js          # Weather/AQI API integration
├── src/
│   ├── components/            # React components
│   │   ├── RealtimeDataCard.tsx    # Live data display
│   │   ├── AiChatWidget.tsx        # AI assistant
│   │   └── ...
│   ├── hooks/
│   │   └── useRealtimeData.ts     # WebSocket hook
│   ├── utils/
│   │   └── aiEngine.ts            # AI calculations
│   ├── config/
│   │   └── system.ts              # Global configuration
│   └── pages/
│       └── Dashboard.tsx          # Main dashboard
├── supabase/
│   └── functions/
│       └── ai-chat/           # Edge function for AI chat
└── package.json
```

---

## 🎤 Hackathon Presentation Guide

### Elevator Pitch (30 seconds)
> "EcoPulse AI is a Real-Time Environmental Intelligence System that tracks and optimizes daily sustainability behavior using AI-driven insights. We process live environmental data through a simulated streaming pipeline inspired by Pathway, combining real-time APIs and AI models to generate actionable sustainability insights."

### Key Talking Points

1. **Real-Time Streaming**
   - "We simulate a streaming pipeline using event-driven architecture"
   - "Live AQI and weather APIs continuously update our system via WebSockets"
   - "Dashboard updates every 3 seconds with real environmental data"

2. **AI System**
   - "Hybrid AI combining rule-based estimation and predictive modeling"
   - "Carbon footprint calculated using EPA emission factors"
   - "AI chatbot uses prompt-based NLP for contextual recommendations"

3. **Impact**
   - "Helps users reduce their carbon footprint through data-driven insights"
   - "Gamification encourages sustainable habits"
   - "Community campaigns drive collective action"

### Demo Flow
1. Show real-time AQI/temperature updates
2. Log a carbon entry and show AI tips
3. Demonstrate AI chat with contextual responses
4. Show leaderboard/gamification features

---

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `VITE_SUPABASE_URL` | Supabase project URL | Yes |
| `VITE_SUPABASE_ANON_KEY` | Supabase anonymous key | Yes |
| `OPENWEATHER_API_KEY` | OpenWeatherMap API key | No |
| `VITE_SOCKET_URL` | Backend server URL | No (default: localhost:3001) |

### Customization

Update `src/config/system.ts` to modify:
- Project name and branding
- Feature flags
- Streaming intervals
- AI configuration

---

## 📝 License

MIT License - feel free to use this project for your own hackathons or personal use.

---

## 🙏 Acknowledgments

- **Pathway** - Inspiration for streaming architecture
- **OpenWeatherMap** - Weather and AQI data
- **Supabase** - Backend infrastructure
- **OpenAI** - GPT-4o-mini for AI chat

---

## 📞 Contact

For questions or support, please open an issue in the repository.

---

**Built with 💚 for a sustainable future**
