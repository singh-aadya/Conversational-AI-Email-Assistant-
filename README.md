#  Conversational AI Email Assistant 

##  Abstract

The **Conversational AI Email Assistant** is an AI-driven virtual assistant that understands natural language commands, generates professional emails, and autonomously sends them through Gmail. By combining conversational AI, smart context management, and browser automation, this project brings real-world task execution to life through seamless user interaction.

---

##  Overview

This project demonstrates the fusion of **Conversational AI**, **Generative AI**, and **Browser Automation** to perform real-world tasks with minimal human intervention. Users can type simple commands, and the assistant will clarify, compose, and send emails in real-time with visual confirmation.

---

##  Architecture Diagram

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

### Component Breakdown:
- **User Input (Chat UI):** Collects user requests naturally without forms.
- **Conversational Agent:** Uses OpenAI's GPT to understand intent and generate responses.
- **Context Manager:** Tracks prior messages to maintain flow and context.
- **Email Generator:** Crafts professional email content dynamically.
- **Browser Automation:** Automates Gmail actions through Puppeteer/Playwright.
- **Visual Feedback:** Displays screenshots after each action for transparency.

---

##  Technology Stack

| Layer                | Technology/Library               | Justification                                           |
|----------------------|------------------------------------|--------------------------------------------------------|
| Conversational AI     | OpenAI GPT API                    | Best-in-class language generation and comprehension     |
| Backend Scripting     | Node.js + Express.js    | Fast, asynchronous, scalable server-side logic          |
| Browser Automation    | Puppeteer            | Reliable headless automation with screenshot capture    |
| UI       | React.js           | Simple, responsive chat interface for interaction       |

---

##  Key Features

✅ **Natural Language Chat Interface:** Talk to the assistant like you would to a human.

✅ **Smart Context Management:** The assistant remembers your inputs and uses them intelligently.

✅ **AI Email Generation:** Emails are composed in a formal, professional tone without manual writing.

✅ **Gmail Automation:** Logins, compositions, and sends without user intervention.

✅ **Visual Feedback:** Screenshots are shared so users can see what actions are being performed.

✅ **Robust Error Handling:** Fail gracefully with user-friendly messages and screenshots on errors.

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

### 3. Configure Environment Variables

Create a `.env` file in the root directory with the following content:

```bash
OPENAI_API_KEY=your_openai_api_key
GMAIL_USER=your_test_gmail_account@gmail.com
GMAIL_PASS=your_test_app_password
```

 **How to get Gmail App Password:**
1. Go to Google Account → Security → App Passwords.
2. Generate a password specifically for "Mail" and "Windows PC".
3. Paste the generated password as `GMAIL_PASS`.

*Note: Do not use personal or production Gmail accounts.*

### 4. Run the Application

```bash
node app.js
```

---

##  How It Works (Step by Step)

1. **User initiates conversation** via the chat interface or CLI.
2. **Assistant extracts intent** (e.g., send a leave application).
3. **Assistant asks clarifying questions** (dates, recipient, reason).
4. **Email content is generated** using GPT with tailored prompts.
5. **Browser Automation:**
   - Opens Gmail
   - Logs in securely
   - Composes email with AI-generated content
   - Sends email
6. **Screenshots captured** after each step are shown back to the user.

---

##  Challenges Faced & Solutions

| Challenge                               | Solution Implemented                                          | Trade-offs / Limitations                                      |
|-----------------------------------------|---------------------------------------------------------------|---------------------------------------------------------------|
| CAPTCHA & 2FA in Gmail Automation       | Used App Passwords & fresh test accounts                      | Not scalable for real accounts; OAuth2 planned for future     |
| Maintaining Context in Conversations    | Implemented message history stored in session memory           | No long-term memory without external storage                   |
| AI Generating Off-Tone Content          | Used detailed system prompts and role instructions             | Still not 100% foolproof—human review may be required          |
| Browser Automation Failures             | Added waitForSelectors, try/catch blocks, and screenshot capture | Adds slight delays to ensure reliability                       |

---

##  Future Improvements

- Implement **OAuth2** for Gmail authentication.
- Add **persistent context memory** using a vector database (Pinecone, Redis, etc.).
- Integrate **voice input and output** for hands-free interaction.
- Build a fully responsive chat UI with **React + Tailwind CSS**.

