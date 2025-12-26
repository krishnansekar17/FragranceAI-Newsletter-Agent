# 🌸 FragranceAI - AI-Powered Daily Newsletter Agent

An intelligent automation system that curates, generates, and delivers daily fragrance newsletters using AI.

![FragranceAI Banner](https://github.com/krishnansekar17/FragranceAI-Newsletter-Agent/blob/25597690810e42c2e3525bbe57544c0a4fdd12be/screenshots/FragranceAI%20UI%20Design.png)

---

## 🤖 Project Category: AI Agent

This project demonstrates an **AI Agent** that autonomously:
- Collects data from multiple sources (Reddit, NewsAPI, Unsplash)
- Processes and merges information
- Generates personalized content using OpenAI
- Delivers emails without human intervention
- Handles user subscriptions intelligently

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🔄 **Auto Data Collection** | Fetches Reddit trends, Google News, Unsplash images |
| 🧠 **AI Content Generation** | GPT-4o-mini creates HTML newsletters |
| 📧 **Smart Subscriptions** | Duplicate detection + welcome emails |
| ⏰ **Scheduled Delivery** | Daily 9 AM automated sends |
| 📊 **Logging System** | Tracks all newsletter deliveries |
| 🎨 **Luxury UI** | Royal-themed landing page |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **n8n** | Workflow automation |
| **OpenAI GPT-4o-mini** | AI content generation |
| **Google Sheets** | Subscriber database |
| **Gmail** | Email delivery |
| **Reddit API** | Trending discussions |
| **NewsAPI** | Fragrance news |
| **Unsplash API** | Hero images |
| **Telegram** | Dev testing |
| **Lovable** | Frontend UI |

---

## 📁 Project Structure

├── workflows/
│ ├── FragranceAI - Daily Newsletter (DEV).json
│ └── FragranceAI - Subscription Webhook (PROD).json
└── screenshots/
└── [Project screenshots]


---

## 🔧 Workflows

### Workflow 1: Subscription Handler
Handles new user signups with duplicate checking and welcome emails.

![Subscription Workflow](https://github.com/krishnansekar17/FragranceAI-Newsletter-Agent/blob/25597690810e42c2e3525bbe57544c0a4fdd12be/screenshots/FragranceAI%20-%20Subscription%20Webhook%20(PROD).png)

**Nodes:**
1. Webhook Trigger
2. Parse Webhook Data
3. Get All Subscribers
4. Check If Email Exists
5. IF (Is New Subscriber?)
6. Save Subscriber (Google Sheets)
7. Send Welcome Email (Gmail)
8. Respond to Webhook

---

### Workflow 2: Daily Newsletter
Generates and sends AI-powered newsletters daily at 9 AM.

![Newsletter Workflow](https://github.com/krishnansekar17/FragranceAI-Newsletter-Agent/blob/25597690810e42c2e3525bbe57544c0a4fdd12be/screenshots/FragranceAI%20Daily%20Newsletter%20Email%20Template.png)

**Nodes:**
1. Schedule Trigger (9 AM Daily)
2. Fetch Reddit Fragrance
3. Fetch Google News
4. Fetch Fragrance Image (Unsplash)
5. Merge All Data
6. Generate Newsletter AI (OpenAI)
7. Extract HTML
8. Get All Subscribers
9. Send Newsletter Email
10. Log Newsletter

---

## 📸 Screenshots

### Landing Page
![Landing Page](https://github.com/krishnansekar17/FragranceAI-Newsletter-Agent/blob/25597690810e42c2e3525bbe57544c0a4fdd12be/screenshots/FragranceAI%20UI%20Design.png)

### Welcome Email
![Welcome Email](https://github.com/krishnansekar17/FragranceAI-Newsletter-Agent/blob/25597690810e42c2e3525bbe57544c0a4fdd12be/screenshots/Welcome%20to%20FragranceAI%20-%20Welcome%20Email%20Copy.png)

### Newsletter Email
![Newsletter Email](https://github.com/krishnansekar17/FragranceAI-Newsletter-Agent/blob/25597690810e42c2e3525bbe57544c0a4fdd12be/screenshots/FragranceAI%20Daily%20Newsletter%20Email%20Template.png)

### Google Sheet Database
![Google Sheet](https://github.com/krishnansekar17/FragranceAI-Newsletter-Agent/blob/25597690810e42c2e3525bbe57544c0a4fdd12be/screenshots/Google%20Sheet%20-%20Subscribers%20and%20Email%20Logs.png)

### Telegram Bot Testing
![Telegram Bot](https://github.com/krishnansekar17/FragranceAI-Newsletter-Agent/blob/25597690810e42c2e3525bbe57544c0a4fdd12be/screenshots/Successful%20Message%20in%20Telegram%20Chat.png)

---

## 🚀 Setup Instructions

### Prerequisites
- n8n instance (self-hosted or cloud)
- Google Account (Sheets + Gmail)
- OpenAI API Key
- NewsAPI Key
- Unsplash Access Key
- Telegram Bot Token

### Installation

1. **Clone this repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/FragranceAI-Newsletter-Agent.git
Import workflows to n8n
Open n8n
Go to Workflows → Import
Select JSON files from /workflows folder
Configure credentials
Google Sheets & Gmail
OpenAI
NewsAPI
Unsplash
Telegram

Create Google Sheet
Sheet 1: Subscribers (email, name, subscribed_date, status, source)
Sheet 2: Newsletter_Log (date, subject, email_count, status)
Activate workflows
📊 Architecture
┌─────────────────┐     ┌─────────────────┐
│  Lovable UI     │────▶│  Webhook        │
│  (Frontend)     │     │  (n8n)          │
└─────────────────┘     └────────┬────────┘
                                 │
                                 ▼
                        ┌─────────────────┐
                        │  Google Sheets  │
                        │  (Database)     │
                        └────────┬────────┘
                                 │
        ┌────────────────────────┼────────────────────────┐
        │                        │                        │
        ▼                        ▼                        ▼
┌───────────────┐    ┌───────────────┐    ┌───────────────┐
│  Reddit API   │    │  NewsAPI      │    │  Unsplash     │
└───────┬───────┘    └───────┬───────┘    └───────┬───────┘
        │                    │                    │
        └────────────────────┼────────────────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │  OpenAI GPT     │
                    │  (AI Agent)     │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │  Gmail          │
                    │  (Delivery)     │
                    └─────────────────┘
🎯 AI Agent Capabilities
This system qualifies as an AI Agent because it:

Perceives - Collects data from multiple APIs
Reasons - Processes and structures information
Acts - Generates content and sends emails
Learns - Adapts content based on season/trends
Autonomous - Operates without human intervention

📝 License
MIT License - Feel free to use and modify!

👨‍💻 Author
Your Name

LinkedIn: https://www.linkedin.com/in/krishnan-sekar-01b1aaaa/
GitHub: @krishnansekar17

🙏 Acknowledgments
n8n Community
OpenAI
Academy Training Program

⭐ Star this repo if you found it helpful!
