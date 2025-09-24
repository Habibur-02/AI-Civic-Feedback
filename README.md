# 🏛️ AI-Powered Civic Feedback & Governance Platform

**HackTheAI 2025 Final Submission – Open Innovation Theme**

A production-ready, AI-driven platform streamlining communication between citizens and government. Built with Streamlit, SQLite, and Google Gemini 2.5 Flash (free API), it provides actionable intelligence, real-time dashboards, secure authentication, and robust analytics—fully functional locally and perfect for hackathon demo.

---

## 📁 Project Structure

![image1](image1)

```
.
├── .streamlit/                # Streamlit UI config
├── reports/                   # Generated analytics/reports
├── LICENSE                    # MIT License
├── README.md                  # Project documentation
├── ai_processing.py           # AI/LLM functions (Gemini + fallback)
├── auth.py                    # Authentication & user management
├── civic_governance.db        # SQLite database file
├── database.py                # DB schema, CRUD, sample data
├── main_app.py                # Main Streamlit app
├── notifications.py           # Notification logic
├── public_dashboard.py        # Public transparency dashboard
├── reports.py                 # Reporting and export
├── requirements.txt           # Python dependencies
├── run.py                     # App runner/launcher
├── sample_data.py             # Demo data population
├── setup.py                   # Project setup utility
```

---

## 🚀 Features

- **Role-Based Authentication**: Secure registration/login for citizens and government officials.
- **AI Categorization & Urgency Scoring**: Google Gemini classifies feedback & ranks urgency (with local fallback).
- **LLM Guidance & Action Plans**: Instant AI-generated advice for citizens, structured action plans for officials.
- **Spam/Quality Detection**: AI flags suspicious or irrelevant feedback.
- **Intermediate Messaging**: Authorities can acknowledge and update citizens on progress.
- **Real-Time Analytics Dashboard**: Interactive charts for category/urgency/status, recent feedback, resolution rate.
- **Public Transparency Dashboard**: Anonymized, live stats for anyone—gov accountability & citizen trust.
- **Notifications**: Real-time alerts for feedback status changes, responses, priority issues.
- **Weekly/Monthly Summary Reports**: AI-generated performance, trend analysis, actionable insights.
- **Sample Data & Demo Accounts**: Pre-populated users, feedback, reports for instant hackathon demo.
- **Privacy Protection**: Anonymized public views, encrypted credentials, soft deletes.
- **Modular, Extensible Code**: Clean Python modules, easy to adapt/scale for any civic context.

---

## 🗄️ Database Design

**Entities:**
- **Users**: `user_id`, `name`, `email`, `password_hash`, `role`, `location`, `phone`, `created_at`, `last_login`, `is_active`
- **Feedback**: `feedback_id`, `user_id`, `title`, `description`, `category`, `severity`, `status`, `ai_response`, `official_response`, `spam_confidence`, `priority_score`, `location_detail`, `created_at`, `updated_at`, `resolved_at`, `is_deleted`, `is_public`
- **Notifications**: `notification_id`, `user_id`, `feedback_id`, `title`, `message`, `type`, `is_read`, `created_at`
- **Reports**: `report_id`, `admin_id`, `report_type`, `parameters`, `file_path`, `file_name`, `generated_at`
- **AI_Logs**: `log_id`, `feedback_id`, `operation`, `input_data`, `output_data`, `confidence_score`, `processing_time`, `created_at`
- **FeedbackHistory**: `history_id`, `feedback_id`, `changed_by`, `field_name`, `old_value`, `new_value`, `change_reason`, `created_at`

---

## 🤖 AI Integration

- **Google Gemini 2.5 Flash API** (free tier):  
  - Feedback categorization
  - Urgency scoring
  - Spam/quality detection
  - Citizen guidance
  - Action plan suggestions
  - Weekly/monthly summary reports
- **Prompt Templates**: Easy to customize in `ai_processing.py`
- **Local Fallbacks**: Rule-based NLP ensures 100% uptime without external API

---

## 📊 Dashboard UI

- **Charts**: Category, urgency, resolution rate (Plotly/Streamlit)
- **Feedback Table**: All feedback, with guidance, action plan, status, and intermediate response
- **Filters**: Category, urgency, dates, status—sidebar controls
- **Submission Forms**: Citizens submit issues, authorities respond/update status
- **Notification Panel**: Real-time feedback alerts and status changes
- **Public Dashboard**: Anonymized, real-time metrics for transparency

---

## 🛠️ Quickstart Guide

### 1. **Clone the Repository**
```bash
git clone https://github.com/your-username/ai-civic-feedback-platform.git
cd ai-civic-feedback-platform
```

### 2. **Install Dependencies**
```bash
pip install -r requirements.txt
```

### 3. **Add Google Gemini API Key (Optional)**
- Get a free key at: https://makersuite.google.com/app/apikey
- Create a `.env` file in root:
  ```
  GOOGLE_API_KEY=your_gemini_api_key_here
  ```
- If omitted, system uses fallback logic for AI.

### 4. **Initialize Project & Sample Data**
```bash
python setup.py
```

### 5. **Run the App**
```bash
python run.py
# or
streamlit run main_app.py
```

### 6. **Access the Dashboard**
- Go to: `http://localhost:8501`
- Use demo credentials or register new accounts.

---

## 👥 Demo Accounts

- **Citizen**  
  Email: `ahmed@email.com`  
  Password: `password123`

- **Admin**  
  Email: `admin@gov.bd`  
  Password: `admin123`

---

## 💡 Customization & Extensions

- **Prompts**: Tweak `ai_processing.py` for guidance/action plans.
- **Database**: Switch to PostgreSQL for production.
- **Styling**: Edit `.streamlit/config.toml` and CSS in `main_app.py`.
- **Features**: Add GIS mapping, upvotes, chat, multi-language, REST API, mobile app.

---

## 🏆 HackTheAI 2025 Ready

- **End-to-End Demo**: Live, functional, AI-powered civic engagement system.
- **ER Diagram & Dataflow**: See docs and code comments for architecture.
- **No Paid APIs Required**: 100% local functionality.
- **Code Quality**: Modular, extensible, fully documented.

---

## 📜 License

MIT License

---

**Built for HackTheAI 2025 — Open Innovation Theme**

---
