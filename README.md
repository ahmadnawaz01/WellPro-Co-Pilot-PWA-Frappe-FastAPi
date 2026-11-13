# 🌟 WellPro Co-Pilot
### Your AI-Powered Personal Health, Wealth & Well-Being Operating System

<p align="center">
  <strong>One platform. Three dimensions of life. One intelligent Co-Pilot.</strong>
</p>

<p align="center">
  <a href="https://github.com/ahmadnawaz01/Well_Pro-Co-Pilot-PWA_React_frontend">Frontend</a> ·
  <a href="https://github.com/ahmadnawaz01/Well-Pro-Co-Pilot-AI-Backend">AI Backend</a> ·
  <a href="https://github.com/ahmadnawaz01/Well-Pro-Co-Pilot-Frappe-Backend">Core Backend</a>
</p>

---

## 🧭 What Is WellPro Co-Pilot?

**WellPro Co-Pilot** is an AI-powered personal life management platform designed to help people understand, monitor, and improve the three fundamental dimensions of their lives:

- 🏃 **Health & Physical Wellness**
- 💰 **Wealth & Financial Stability**
- 🤝 **Social & Emotional Well-Being**

Most people manage these areas separately. They use different applications for fitness, personal finances, daily habits, and social activities. As a result, their information becomes fragmented, and understanding the bigger picture becomes difficult.

WellPro brings these dimensions together into one intelligent ecosystem.

Instead of manually entering information into complicated forms, users can interact with their personal Co-Pilot through **voice messages, photographs, documents, and natural language**.

AI processes the information, extracts meaningful data, organizes it into structured records, and sends it to the core backend. The platform then updates wellbeing indicators and presents meaningful insights through a unified dashboard.

The goal is simple:

> Make tracking your life effortless, understanding your progress easier, and making better everyday decisions more intelligent.

---

## 🎯 The Vision

Imagine starting your day and simply telling your personal Co-Pilot:

- "I slept for 7.5 hours and walked 8,000 steps."
- "I spent 1,500 rupees on groceries."
- "I had lunch with my friends today."
- "I received 50,000 rupees from my freelance work."

Instead of filling out multiple forms, WellPro understands the information, identifies the relevant categories, and transforms your updates into structured personal records.

Over time, these records help build a more complete picture of your life.

Your Co-Pilot can help you explore questions such as:

- How is my physical health progressing?
- Where is most of my money going?
- Am I maintaining a healthy balance between work and social life?
- How has my overall wellbeing changed over the last 30 days?
- Which areas of my life need more attention?

**The long-term vision is to create a personal AI companion that turns everyday life information into meaningful, measurable insights.**

---

## 💡 The Problem We Are Solving

| Traditional Approach | WellPro Approach |
|---|---|
| Separate applications for different life activities | One unified personal platform |
| Manual entry through lengthy forms | Natural language, voice, and image-based capture |
| Fragmented personal information | Centralized health, financial, and social records |
| Difficult-to-understand raw data | AI-assisted summaries and insights |
| Limited understanding of overall wellbeing | Multi-dimensional wellbeing scoring |
| Internet-dependent data entry | Offline-first capture and synchronization |

WellPro aims to reduce the effort required to track everyday activities while making personal information more useful.

---

## 🏗️ System Architecture

WellPro uses a **three-repository, service-oriented architecture**.

Each repository has a dedicated responsibility, allowing the frontend, AI intelligence layer, and core business backend to evolve independently.

### High-Level Architecture

```text
                         ┌──────────────────────────────┐
                         │          THE USER             │
                         │                              │
                         │ Voice · Text · Images · Data │
                         └──────────────┬───────────────┘
                                        │
                                        ▼
                 ┌─────────────────────────────────────────┐
                 │          REACT 19 PWA FRONTEND           │
                 │                                         │
                 │  Dashboard · Life Feed · AI Capture     │
                 │  Co-Pilot Chat · Authentication         │
                 │                                         │
                 │  IndexedDB · Offline Queue · PWA        │
                 └──────────────────┬──────────────────────┘
                                    │
                    ┌───────────────┴────────────────┐
                    │                                │
                    ▼                                ▼
       ┌────────────────────────┐       ┌────────────────────────┐
       │   FASTAPI AI BACKEND   │       │   FRAPPE ERP BACKEND   │
       │                        │       │                        │
       │  Audio Transcription   │       │  Authentication        │
       │  Vision / OCR          │       │  User Management       │
       │  Text Understanding    │       │  Data Management       │
       │  AI Agent / Chatbot     │       │  Wellbeing Scoring     │
       │  AI Tool Execution     │       │  Dashboard Analytics   │
       │                        │       │                        │
       └───────────┬────────────┘       └────────────┬───────────┘
                   │                                 │
                   ▼                                 ▼
       ┌────────────────────────┐       ┌────────────────────────┐
       │      MongoDB Atlas     │       │         MariaDB        │
       │                        │       │                        │
       │ AI Chat State & Memory │       │ Structured User Data   │
       │ Session Persistence    │       │ Health / Finance       │
       │                        │       │ Social / Scores        │
       └────────────────────────┘       └────────────────────────┘
```

### Three Main Components

| Component | Repository | Responsibility |
|---|---|---|
| Frontend | `Well_Pro-Co-Pilot-PWA_React_frontend` | User interface, PWA, dashboards, offline functionality |
| AI Intelligence | `Well-Pro-Co-Pilot-AI-Backend` | Voice processing, image understanding, conversational AI and agent tools |
| Core Backend | `Well-Pro-Co-Pilot-Frappe-Backend` | Authentication, structured records, database management and wellbeing scoring |

### Why Three Separate Repositories?

This separation creates a modular architecture:

- The frontend can evolve without changing the AI service.
- AI providers and models can be changed without rebuilding the core backend.
- The core backend remains responsible for structured data and authoritative business logic.
- Each service can be developed, tested, maintained, and deployed independently.

The repositories are connected in this main repository through **Git Submodules**. Each component retains its own Git history.

---

## 🔄 How Does WellPro Work?

Here is an example of what happens when a user records a voice update.

### Example: Voice-Based Life Tracking

**User says:**

> "Today I slept for 7 hours, walked 8,000 steps, and spent 1,200 rupees on groceries."

**Step 1 — Capture**

The user records a voice message using the React PWA.

**Step 2 — AI Processing**

The frontend sends the audio to the FastAPI AI service.

The AI service processes the audio, transcribes it, and extracts relevant information.

**Step 3 — Structured Data Extraction**

The AI identifies different pieces of information:

```json
{
  "health": {
    "sleep_hours": 7,
    "steps": 8000
  },
  "financial": [
    {
      "type": "Expense",
      "amount": 1200,
      "category": "Groceries"
    }
  ]
}
```

*Illustrative example of the intended structured output.*

**Step 4 — Backend Integration**

The structured information is dispatched to the relevant Frappe endpoints.

The Frappe backend validates the request, associates records with the authenticated user, and stores the information in the appropriate DocTypes.

**Step 5 — Wellbeing Score Calculation**

The scoring engine processes the available records and updates the relevant daily wellbeing indicators.

**Step 6 — Dashboard Update**

The React frontend retrieves updated information and displays the results through the dashboard and life feed.

```text
Voice Input
    ↓
React PWA
    ↓
FastAPI AI Service
    ↓
Transcription & AI Extraction
    ↓
Structured JSON
    ↓
Frappe Backend
    ↓
MariaDB Records
    ↓
Wellbeing Score Calculation
    ↓
Dashboard & Life Feed
```

The same overall architecture supports text-based and image-based data capture.

---

## ✨ Core Features

### 1. 🏃 Health & Physical Wellness

Track important personal health and activity indicators.

Examples include:

- Sleep duration
- Daily steps
- Exercise and active minutes
- Water intake
- Nutrition and dietary information
- Workout and fitness activities

The system organizes health information into structured records that can contribute to health-related wellbeing indicators.

### 2. 💰 Wealth & Financial Management

Understand personal financial activity and progress.

Examples include:

- Income tracking
- Expense tracking
- Transaction categories
- Savings information
- Emergency fund tracking
- Outstanding debt
- Financial snapshots

The financial dimension helps users understand their spending patterns and financial position.

### 3. 🤝 Social & Emotional Well-Being

Track personal experiences and subjective wellbeing indicators.

Examples include:

- Social interactions
- Time spent with friends and family
- Connection and relationship quality
- Mood and energy
- Stress and loneliness check-ins

These indicators help users reflect on their social and emotional wellbeing.

### 4. 🤖 AI-Powered Multimodal Data Capture

WellPro supports multiple ways to provide personal information.

| Input Method | AI Capability |
|---|---|
| 🎙 Voice | Audio transcription and structured information extraction |
| 📷 Images | Receipt and document understanding |
| 📝 Text | Natural-language interpretation and record extraction |
| 📄 Documents | Vision-based document processing where supported |

The objective is to turn unstructured everyday information into useful structured records.

### 5. 💬 Intelligent AI Co-Pilot

The platform includes a conversational AI assistant powered by an agentic ReAct workflow.

The assistant is designed to work with backend tools to support tasks such as:

- Answering questions about personal records
- Retrieving historical information
- Understanding wellbeing trends
- Creating and modifying records
- Inspecting dashboard information
- Recalculating wellbeing scores
- Managing supported scoring goals

Conversation state is persisted using MongoDB-backed session storage.

### 6. 📊 Unified Wellbeing Dashboard

WellPro brings the three dimensions together into one dashboard.

The scoring system provides:

- Health score
- Financial score
- Social wellbeing score
- Overall wellbeing score
- Historical score information
- Trend analysis
- Confidence indicators
- Goal-related information

Scores are designed to make progress easier to understand rather than simply displaying disconnected measurements.

### 7. 📱 Offline-First Progressive Web App

WellPro is designed to remain useful when internet connectivity is unavailable.

Frontend capabilities include:

- Local data caching through IndexedDB
- Offline record creation
- Local persistence of queued requests
- Audio and image payload storage
- FIFO outbound synchronization
- Automatic synchronization when connectivity returns
- PWA installation support

When the network becomes available, pending operations can be synchronized with the backend.

---

## 🧠 The Intelligence Layer

The FastAPI service acts as the independent AI processing layer.

Its responsibilities include:

| Capability | Technology / Service |
|---|---|
| API framework | FastAPI |
| Audio transcription | Groq Whisper |
| Image and document understanding | Vision models through OpenRouter |
| Conversational reasoning | Gemini |
| Agent workflow | ReAct-style agent |
| Persistent conversation state | MongoDB Atlas |

### Why Keep AI Separate?

AI models and providers change rapidly.

By isolating AI functionality in a separate service, WellPro can introduce or replace models without redesigning its database structure or frontend application.

The AI service interprets information and coordinates supported tools, while the Frappe backend remains the authoritative system for core user records.

---

## ⚙️ Core Backend & Wellbeing Intelligence

The Frappe backend is the central data and business-logic layer.

Built using Frappe Framework and ERPNext v15, it provides:

- User authentication and session management
- Token-based API authentication
- User-scoped record access
- Custom DocTypes
- Secure CRUD operations
- Multi-domain data ingestion
- Wellbeing score calculations
- Dashboard metrics
- Historical data retrieval
- Scoring goal configuration

### Main Data Models

| DocType | Purpose |
|---|---|
| `Health Daily Record` | Daily health measurements |
| `Health Activity` | Individual fitness activities |
| `Financial Transaction` | Income, expenses and other transactions |
| `Financial Snapshot` | Financial position and balances |
| `Financial Category` | Financial transaction categorization |
| `Social Activity` | Social interactions |
| `Subjective Wellbeing Checkin` | Mood, energy and other self-reported indicators |
| `Wellbeing Daily Score` | Calculated wellbeing scores |
| `WellPro Profile` | User profile and preferences |
| `User Consent Preference` | User consent settings |

### Multi-Dimensional Scoring

The platform calculates scores across three dimensions:

```text
                  WELLPRO WELLBEING ENGINE
                            |
             ┌──────────────┼──────────────┐
             |              |              |
             ▼              ▼              ▼
        HEALTH SCORE   FINANCIAL SCORE  SOCIAL SCORE
             |              |              |
             └──────────────┼──────────────┘
                            |
                            ▼
                     OVERALL SCORE
                            |
                            ▼
                  DASHBOARD & ANALYTICS
```

The scoring implementation includes recency weighting, confidence adjustments, configurable goals, and historical calculations.

The intention is to make scores responsive to recent user activity while accounting for the amount and quality of available information.

---

## 🧰 Technology Stack

### Frontend

- React 19
- Vite
- Tailwind CSS v4
- JavaScript
- Axios
- TanStack Query
- IndexedDB
- Workbox / PWA tooling
- Lucide React

### AI Backend

- Python
- FastAPI
- Gemini
- Groq Whisper
- OpenRouter Vision
- MongoDB Atlas
- Agentic ReAct workflow

### Core Backend

- Python
- Frappe Framework v15
- ERPNext v15
- MariaDB
- Frappe REST API
- Custom DocTypes
- Background jobs and scheduled processing

### Development & Integration

- Git and GitHub
- Git Submodules
- REST APIs
- JSON
- Environment-based configuration
- Postman for API testing

---

## 📂 Main Repository Structure

This repository acts as the parent project and connects all three independently maintained components.

```text
WellPro-Co-Pilot/
│
├── frontend/                 # React PWA Git Submodule
│
├── fastapi-backend/          # AI Intelligence Git Submodule
│
├── frappe-backend/           # Core Frappe Backend Git Submodule
│
├── docs/                     # Architecture and project documentation
│
├── screenshots/              # Application screenshots
│
├── .gitmodules               # Git submodule configuration
│
└── README.md                 # Main project documentation
```

### Individual Repositories

**1. Frontend — React PWA**

[Well_Pro-Co-Pilot-PWA_React_frontend](https://github.com/ahmadnawaz01/Well_Pro-Co-Pilot-PWA_React_frontend)

Responsible for the user experience, life feed, dashboards, AI capture interface, chatbot, and offline functionality.

**2. AI Backend — FastAPI**

[Well-Pro-Co-Pilot-AI-Backend](https://github.com/ahmadnawaz01/Well-Pro-Co-Pilot-AI-Backend)

Responsible for AI processing, audio transcription, image understanding, natural-language extraction, and the conversational agent.

**3. Core Backend — Frappe / ERPNext**

[Well-Pro-Co-Pilot-Frappe-Backend](https://github.com/ahmadnawaz01/Well-Pro-Co-Pilot-Frappe-Backend)

Responsible for user authentication, structured data storage, record management, wellbeing scoring, and analytics.

---

## 🚀 Getting Started

### Prerequisites

Install the following tools before running the complete system:

- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/) and npm
- [Python](https://www.python.org/)
- [Frappe Bench](https://frappeframework.com/docs/user/en/bench)
- MariaDB
- MongoDB Atlas account or compatible MongoDB deployment
- API credentials for the AI providers you configure

### 1. Clone the Main Repository

Use `--recurse-submodules` to download the three component repositories together.

```bash
git clone --recurse-submodules https://github.com/ahmadnawaz01/WellPro-Co-Pilot.git

cd WellPro-Co-Pilot
```

If you already cloned the main repository without its submodules:

```bash
git submodule update --init --recursive
```

### 2. Run the React Frontend

```bash
cd frontend

npm install
```

Configure the frontend environment variables using the component's `.env.example` or README instructions.

Typical local configuration:

```env
VITE_FRAPPE_BASE_URL=http://localhost:8000
VITE_FASTAPI_BASE_URL=http://localhost:8080
```

Start the frontend:

```bash
npm run dev
```

The development server is normally available at:

```text
http://localhost:5173
```

### 3. Run the FastAPI AI Backend

Open another terminal:

```bash
cd WellPro-Co-Pilot/fastapi-backend
```

Create and activate a virtual environment:

```bash
python -m venv venv
```

Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

Install the dependencies using the requirements file provided by the AI backend:

```bash
pip install -r requirements.txt
```

Configure the required environment variables using the AI backend's environment template.

Start the service using the entry point and command documented in that repository.

The default development API address is:

```text
http://localhost:8080
```

### 4. Run the Frappe Backend

Follow the setup instructions in:

[Well-Pro-Co-Pilot-Frappe-Backend](https://github.com/ahmadnawaz01/Well-Pro-Co-Pilot-Frappe-Backend)

The Frappe development environment should have the required application installed on a site.

For a typical local Frappe Bench setup:

```bash
cd frappe-bench

bench start
```

The default local Frappe address is:

```text
http://localhost:8000
```

### 5. Run the Complete System

Once all three services are configured and running:

| Service | Local Address |
|---|---|
| React PWA | `http://localhost:5173` |
| FastAPI AI Backend | `http://localhost:8080` |
| Frappe Backend | `http://localhost:8000` |

Open the frontend in your browser and configure the appropriate backend URLs and authentication.

**Important:** Each component has its own dependencies, environment variables, and setup requirements. Refer to its individual README for the complete configuration.

---

## 🔐 Security & Data Privacy

WellPro handles personal information, including health, financial, and social data. Security and privacy are therefore important architectural considerations.

The platform incorporates or is designed around the following safeguards:

- Token-based authentication for protected backend APIs.
- User-scoped access to personal records.
- Server-side ownership enforcement.
- Restricted DocType access through allowlisted operations.
- Environment variables for service credentials.
- Explicit consent preferences for supported data-processing features.
- Separation of AI processing from the core data-management layer.

### Important Security Practices

- Never commit `.env` files or API secrets.
- Use `.env.example` files containing placeholders.
- Do not expose private API credentials in frontend code.
- Use HTTPS for deployed services.
- Restrict database access and secure backups.
- Review access permissions before production deployment.

WellPro is intended to support personal decision-making. Its wellbeing indicators are informational and should not be treated as medical diagnoses, professional financial advice, or a replacement for qualified professionals.

---

## 🗺️ Development Roadmap

WellPro is being developed as an evolving personal intelligence platform.

| Phase | Focus | Goal |
|---|---|---|
| 1 | Foundation | Architecture, repositories, data models and UI |
| 2 | Core Platform | Authentication, personal records and life feed |
| 3 | AI Capture | Voice, text and image-based information extraction |
| 4 | Wellbeing Intelligence | Multi-dimensional scores and analytics |
| 5 | AI Co-Pilot | Conversational assistant and tool integration |
| 6 | Optimization | Testing, privacy, performance and deployment |

### Future Possibilities

- More advanced personalized recommendations.
- Weekly and monthly wellbeing reports.
- Intelligent reminders and habit assistance.
- Expanded health-data integrations.
- More advanced financial analytics.
- Improved multilingual voice interaction.
- Additional AI providers and model choices.
- Production deployment and monitoring.

These are development directions, not a claim that every capability is already implemented.

---

## 📸 Screenshots & Demo

Screenshots and demonstrations will be maintained in the `screenshots/` directory.

Suggested showcase sections:

```text
screenshots/
│
├── dashboard.png
├── life-feed.png
├── ai-capture.png
├── copilot-chat.png
├── health-analytics.png
├── financial-analytics.png
└── mobile-pwa.png
```

Add screenshots here as the application interface is finalized.

---

## 🧩 Why This Project Is Different

WellPro is not simply another chatbot or personal tracking application.

It brings together several engineering disciplines into one integrated system:

- **Full-stack engineering:** A React application connected to independent backend services.
- **AI engineering:** Multimodal processing and agentic tool-based interaction.
- **Backend engineering:** Structured data models, authentication, APIs and business logic.
- **Data engineering:** Personal records, historical information and analytics.
- **Offline-first engineering:** Local persistence and synchronization.
- **System architecture:** Independently maintained services connected through well-defined interfaces.

The broader objective is to demonstrate how AI can become a practical part of everyday personal life management.

---

## 🤝 Contributing

Contributions, suggestions, and feedback are welcome.

Because the system consists of three independent repositories, contributions should generally be made to the relevant component:

1. Frontend improvements → [Frontend Repository](https://github.com/ahmadnawaz01/Well_Pro-Co-Pilot-PWA_React_frontend)
2. AI improvements → [AI Backend Repository](https://github.com/ahmadnawaz01/Well-Pro-Co-Pilot-AI-Backend)
3. Core backend improvements → [Frappe Backend Repository](https://github.com/ahmadnawaz01/Well-Pro-Co-Pilot-Frappe-Backend)

For changes affecting multiple components, ensure API contracts and integration behavior remain compatible.

---

## 👨‍💻 Project Author

**Ahmad Nawaz**

Full-Stack Developer | AI/ML & Generative AI Enthusiast

GitHub: [@ahmadnawaz01](https://github.com/ahmadnawaz01)

---

## 📄 License

The main repository connects multiple independently maintained repositories.

Please refer to the license files in each component repository for their respective licensing terms. A root-level license should be added once the licensing terms for the complete project have been confirmed.

---

<p align="center">
  <strong>🌱 WellPro Co-Pilot</strong>
  <br/>
  <em>Understand your life. Measure your progress. Make better decisions.</em>
  <br/><br/>
  Built with ❤️ by Ahmad Nawaz
</p>
