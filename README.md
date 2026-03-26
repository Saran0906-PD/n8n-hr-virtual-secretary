# 🤖 AI Email Automation Assistant  
### Multi-Workflow Intelligent System

An intelligent AI-powered automation system that processes incoming emails and dynamically performs multiple tasks such as meeting scheduling, urgent alerting, resume analysis, task reminders, and daily summaries.

---

## 📖 Overview

Managing emails manually for scheduling meetings, handling urgent requests, and tracking tasks is inefficient and time-consuming.

This project solves that problem by building a fully automated AI assistant using **n8n workflows**, integrating multiple services to understand and act on emails without human intervention.

---

## ❗ Problem Statement

Organizations and individuals receive a large number of emails daily. Manually:
- Scheduling meetings
- Identifying urgent messages
- Tracking tasks
- Reviewing resumes  

is inefficient and error-prone.

This system automates the entire process intelligently.

---

## 💡 Key Features

- 📧 Email-based automation using Gmail Trigger
- 🧠 Intelligent email classification (meeting, urgent, task, resume)
- 📅 Meeting scheduling with real-time conflict detection
- 🚨 Instant Telegram alerts for urgent emails
- 📄 AI-based resume analysis & scoring (Gemini API)
- ⏰ Automated task reminders
- 📊 Daily summary reports
- 🔁 Fully automated workflows with zero manual effort

---

## 🧠 Core Modules

### 1. Email Classification Engine
- Uses rules + logic to categorize emails:
  - meeting
  - urgent
  - task
  - job (resume)

---

### 2. Meeting Automation System
- Extracts user-selected slot
- Checks Google Calendar availability
- Prevents double booking
- Sends alternative slots if unavailable
- Confirms meeting via email

---

### 3. Urgent Alert System
- Detects high-priority emails
- Sends instant alerts via Telegram

---

### 4. Resume Analyzer (AI Feature)
- Extracts content from PDF resumes
- Uses Gemini AI for evaluation
- Generates a score
- Sends alert if score > 80%

---

### 5. Task Reminder System
- Runs on scheduled intervals
- Fetches pending tasks from database
- Sends reminders via Telegram

---

### 6. Daily Summary Generator
- Runs on cron schedule
- Summarizes system activity
- Sends daily report

---

## 🏗️ System Architecture

The system follows an event-driven architecture:

1. Gmail Trigger captures incoming email  
2. JavaScript parses content  
3. Switch node classifies intent  
4. Routes to specialized workflows:
   - Meeting Engine  
   - Urgency Engine  
   - Resume Analyzer  
   - Task Manager  
5. External APIs execute actions  
6. Responses sent via Email / Telegram  

---

## 🔄 Data Flow

Email → Parsing → Classification → Decision Engine → Action Execution → Database Update → Notification

---

## ⚙️ Tech Stack

- **Automation Engine**: n8n  
- **Programming**: JavaScript  
- **Database**: PostgreSQL  
- **AI Model**: Google Gemini  
- **APIs Used**:
  - Gmail API  
  - Google Calendar API  
  - Telegram API  

---

## 🗄️ Database Design

### meetings table
| Column        | Type       |
|--------------|-----------|
| id           | SERIAL     |
| sender       | TEXT       |
| selectedSlot | TIMESTAMP  |
| status       | TEXT       |
| created_at   | TIMESTAMP  |

---

### tasks table
| Column  | Type |
|--------|------|
| id     | SERIAL |
| task   | TEXT |
| deadline | TIMESTAMP |
| status | TEXT |

---

### logs table
| Column | Type |
|--------|------|
| id     | SERIAL |
| type   | TEXT |
| message| TEXT |
| timestamp | TIMESTAMP |

---

## 📸 Screenshots

### Main Workflow
Shows full automation pipeline from email intake to execution.

### Meeting Automation
Handles scheduling and conflict resolution.

### Resume Analyzer
AI-based resume scoring system.

### Task Reminder
Automated notification system.

---

## 🧪 Example Use Cases

### 📅 Meeting Request
**Input:**
"Hey, I need a meeting tomorrow. Slot 2 works."

**System:**
- Checks availability  
- Books meeting OR suggests alternatives  

---

### 🚨 Urgent Email
**Input:**
"This is urgent, please respond ASAP"

**System:**
- Detects urgency  
- Sends Telegram alert  

---

### 📄 Resume Submission
**Input:**
Resume PDF  

**System:**
- Extracts content  
- Scores resume  
- Sends alert if score > 80%  

---

## 📊 Results

- Reduced manual effort by ~90%
- Automated real-time email handling
- Accurate classification of requests
- Efficient multi-task automation

---

## ⚠️ Challenges Faced

- Managing multiple workflows simultaneously  
- Avoiding duplicate bookings  
- Correctly classifying email intent  
- Handling asynchronous execution in n8n  

---

## 📈 Future Improvements

- NLP-based intent detection  
- Multi-user support  
- Web dashboard  
- WhatsApp integration  
- Voice assistant integration  

---

## 🏁 Conclusion

This project demonstrates how AI and automation can be combined to build a powerful intelligent assistant capable of handling real-world workflows efficiently with minimal human intervention.

---

## 👨‍💻 Author

**Saran Periyasamy**  
B.Tech AIML  
VIT Vellore  

---
