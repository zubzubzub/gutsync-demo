# GutSync - AI-Powered Crohn's Disease Tracker

<p align="center">
  <img src="https://img.shields.io/badge/Status-Demo-green" alt="Status">
  <img src="https://img.shields.io/badge/Platform-Web-blue" alt="Platform">
  <img src="https://img.shields.io/badge/License-Prototype-yellow" alt="License">
</p>

## 🌿 Overview

GutSync is an AI-powered symptom tracker designed specifically for Crohn's Disease patients. It helps users:

- **Track daily symptoms** with medical-grade precision (Bristol Stool Scale, pain mapping, etc.)
- **Spot patterns** before they become flares
- **Generate doctor-ready reports** with Harvey-Bradshaw Index scoring
- **Maintain medication adherence** with smart tracking

## ✨ Features

### 1. Onboarding Flow
- Diagnosis date capture
- Medication setup (common Crohn's meds pre-loaded)
- Optional medication photo capture for reference

### 2. Daily Check-in
- **Bowel movements**: Count + Bristol Stool Scale (visual types 1-7)
- **Pain assessment**: 0-10 scale + interactive body map
- **Medications**: Checkbox list based on your regimen
- **Energy/fatigue**: 5-level scale with emoji indicators
- **Extra symptoms**: Joint pain, skin issues, eye problems, nausea, mouth sores, fever

### 3. Dashboard
- Logging streak tracker
- Medication adherence percentage
- AI insight card with flare risk assessment
- Trend charts (pain & bowel movements over time)
- Recent logs summary

### 4. AI Insights
- **Flare Risk Indicator**: Green/Yellow/Red based on recent patterns
- **7-Day Summary**: Aggregated metrics
- **Pattern Detection**: Identifies recurring extra symptoms
- **Mock Integrations**: Apple Health & WHOOP connection UI (demo)

### 5. Doctor Report
- Configurable date range (7/14/30/90 days)
- Harvey-Bradshaw Index calculation
- Downloadable text report
- Summary statistics ready for GI appointments

## 🚀 Quick Start

### Option 1: Open Directly
Simply open `index.html` in any modern browser:
```bash
open index.html
# or
google-chrome index.html
```

### Option 2: Local Server
```bash
# Using Python
python -m http.server 8000
# Then visit http://localhost:8000

# Using Node.js
npx serve .
# Then visit http://localhost:3000
```

### Option 3: Deploy to Vercel/Netlify
Just drag the `index.html` file to your deployment dashboard.

## 📱 Mobile Experience

The app is fully responsive and designed for mobile-first usage:
- Touch-optimized controls
- Safe area support for notched devices
- Smooth animations
- No app install required - works as a PWA

## 🧠 How the AI Works (Rule-Based Demo)

For this demo, insights are generated using rule-based logic:

```
Flare Risk Score =
  (Pain > 5) → +25 points
  (BM > 5/day) → +20 points
  (3+ loose stool days) → +25 points
  (High fatigue) → +15 points
  (Increasing pain trend) → +15 points

Risk Levels:
  0-30%  → Green (Stable)
  30-70% → Yellow (Caution)
  70%+   → Red (Elevated)
```

In production, this would be replaced with ML models trained on patient data, incorporating:
- HRV/sleep data from wearables
- Personalized baselines
- Temporal pattern recognition (LSTM)

## 📊 Data Model

```javascript
// User Profile
{
  diagnosisDate: "2020-01-15",
  medications: ["Humira", "Prednisone"],
  medPhoto: "base64...",
  createdAt: "2024-01-31T..."
}

// Daily Log
{
  date: "2024-01-31",
  bowelCount: 4,
  bristolType: 5,
  painLevel: 3,
  painLocation: "rlq",
  fatigue: 3,
  medsTaken: ["Humira"],
  extras: ["joint_pain"],
  notes: "Felt tired after lunch",
  hbi: 5
}
```

All data is stored in localStorage for the demo. Production would use:
- Encrypted cloud storage (Supabase/Firebase)
- HIPAA-compliant backend
- Optional Apple Health/Google Fit sync

## 📋 Harvey-Bradshaw Index

The app calculates an estimated HBI score based on daily logs:

| Score | Interpretation |
|-------|----------------|
| < 5 | Remission |
| 5-7 | Mild disease |
| 8-16 | Moderate disease |
| > 16 | Severe disease |

**Components tracked:**
- General well-being (energy level)
- Abdominal pain
- Number of liquid stools

## 🔮 Future Enhancements

### Phase 2: Wearable Integration
- Apple HealthKit (HRV, sleep, heart rate)
- WHOOP API (recovery score, strain)
- Smart scale integration (Withings)

### Phase 3: Advanced AI
- Personalized flare prediction (24-72 hour lead time)
- Food trigger identification
- Medication response patterns

### Phase 4: Clinical Integration
- Epic MyChart FHIR integration
- Lab result import (CRP, calprotectin)
- Provider dashboard

## 🛡️ Privacy

- All data stored locally on device (demo)
- No server communication
- No tracking or analytics
- HIPAA-compliant design principles

## 📸 Screenshots

### Onboarding
```
┌─────────────────────────┐
│        🌿               │
│   Welcome to GutSync    │
│                         │
│  📊 Smart tracking      │
│  🤖 AI predictions      │
│  📋 Doctor reports      │
│                         │
│   [ Get Started ]       │
└─────────────────────────┘
```

### Dashboard
```
┌─────────────────────────┐
│ GutSync         🌿      │
│ Monday, January 31      │
│ ┌─────────┬─────────┐   │
│ │ 7 Days  │ 85%     │   │
│ │ Streak🔥│ Adherence│   │
│ └─────────┴─────────┘   │
│ ┌───────────────────┐   │
│ │💚 Patterns stable!│   │
│ │ Pain avg 2.3/10   │   │
│ └───────────────────┘   │
│                         │
│ [📝 Daily Check-in ]    │
│                         │
│   📈 Trends Chart       │
└─────────────────────────┘
```

### Daily Check-in
```
┌─────────────────────────┐
│ ← Cancel    Check-in    │
│─────────────────────────│
│ Bowel Movements Today   │
│    [ - ]   4   [ + ]    │
│                         │
│ Bristol Stool Type      │
│ ┌─────────────────────┐ │
│ │ 4 │ Smooth snake    │ │
│ │ ● │ Ideal           │ │
│ └─────────────────────┘ │
│                         │
│      [ Next → ]         │
└─────────────────────────┘
```

## 🤝 Contributing

This is a demo/prototype. For production development inquiries, please reach out.

## 📄 License

Prototype - All rights reserved.

---

Built with ❤️ for the IBD community
