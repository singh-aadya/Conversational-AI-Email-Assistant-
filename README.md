# Conversational-AI-Email-Assistant

## Overview

The **Conversational AI Email Assistant** is an intelligent AI-powered agent that can autonomously understand user commands, generate professional emails, and send them via Gmail—all through a natural conversational interface. This project demonstrates the fusion of **Conversational AI**, **Generative AI**, and **Browser Automation** to perform real-world tasks with minimal human intervention.


## Architecture Diagram

```
User Input (Chat UI) 
        ↓
Conversational Agent (Node.js + OpenAI GPT API)
        ↓
Context Manager (Maintains chat history & user preferences)
        ↓
Email Generator (AI-generated Subject + Body)
        ↓
Browser Automation (Puppeteer/Playwright)
        ↓
Gmail Actions (Login → Compose → Send Email)
        ↓
Real-Time Visual Feedback (Screenshots at Each Step)
```

---

##  Technology Stack

| Layer                | Technology/Library               | Reason for Choice                                      |
|----------------------|------------------------------------|--------------------------------------------------------|
| Conversational AI     | OpenAI GPT API                    | Powerful natural language understanding & generation    |
| Backend Scripting     | Node.js (Express.js optional)      | Fast, lightweight, async-friendly                      |
| Browser Automation    | Puppeteer / Playwright            | Headless browser control with screenshot capabilities   |
| UI                    | React.js / Basic HTML-CSS-JS       | Clean chat interface                                   |

---

##  Key Features

✅ Conversational interface — natural, human-like flow  
✅ Smart context management — remembers previous user inputs  
✅ AI-generated email content (subject + body)  
✅ Browser automation — logs in, composes, and sends emails via Gmail  
✅ Real-time visual feedback — shows screenshots of every step  
✅ Basic error handling & edge-case detection  

---

##  Setup Instructions

### 1. Clone this Repository

```bash
git clone https://github.com/YourUsername/conversational-ai-email-assistant.git
cd conversational-ai-email-assistant
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables (`.env`)

```bash
OPENAI_API_KEY=your_openai_api_key
GMAIL_USER=your_test_gmail_account@gmail.com
GMAIL_PASS=your_test_app_password
```

 **Note:**  
For security reasons, use **App Passwords** for Gmail and never use your personal account.

### 4. Run the Application

```bash
node app.js
```

---

##  How It Works (Step by Step)

1. **User inputs natural language** (e.g., “I need to send a leave application”).
2. **AI understands intent** and asks clarifying questions (dates, recipient email, reason).
3. **Generates email content** using GPT API.
4. **Automates Gmail in real-time** to:
   - Log in securely
   - Compose the email
   - Send the email
5. **Captures screenshots** along the way and shares them back with the user.

---

##  Challenges Faced & Solutions

| Challenge                               | Solution Implemented                                          |
|-----------------------------------------|---------------------------------------------------------------|
| CAPTCHA & 2FA in Gmail Automation       | Used fresh Gmail accounts & app passwords to bypass CAPTCHA    |
| Maintaining Context in Conversations    | Implemented simple memory buffer to store prior inputs         |
| AI Content Not Always Professional      | Prompt engineering with role-specific instructions to GPT      |
| Slow or Broken Automation               | Introduced retries, waits, and error handling in browser logic |

---

##  Future Improvements

- Implement **OAuth2** for safer Gmail access  
- Enhance **context memory** using vector embeddings (LangChain)  
- Add **voice input/output** for a fully hands-free experience  
- Polish the UI for broader user adoption  
