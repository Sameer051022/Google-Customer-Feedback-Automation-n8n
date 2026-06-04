# 🔄 Google Customer Feedback Automation (n8n)

> Fully automated n8n workflow that handles Google Form customer feedback — checks sentiment, sends discount emails for positive responses, and logs negative feedback to Google Sheets. **Zero manual entry. Fully event-driven.**

![n8n](https://img.shields.io/badge/n8n-Automation-orange?style=for-the-badge&logo=n8n)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-Integration-34A853?style=for-the-badge&logo=google-sheets)
![Gmail](https://img.shields.io/badge/Gmail-Email%20Automation-EA4335?style=for-the-badge&logo=gmail)
![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=for-the-badge)

---

## 📋 Overview

A client asked: *"Can n8n automatically handle customer feedback and send discounts — without anyone touching it?"*

Built this in an afternoon. The workflow:

1. ✅ Customer submits a Google Form with their feedback
2. ✅ n8n checks — is the feedback **positive** or **negative**?
3. ✅ **Positive** → discount email sent automatically via Gmail
4. ✅ **Negative** → logged in Google Sheets for team follow-up
5. ✅ Every response saved — **zero manual entry**

The whole thing runs without a single person involved.

---

## 🏗️ Workflow Architecture

```
[Google Form Submission]
         ↓
  [n8n Trigger Node]
         ↓
  [IF Node: Sentiment Check]
    ↙              ↘
[Positive]       [Negative]
    ↓                 ↓
[Gmail Node]   [Google Sheets Node]
Send Discount    Log for Follow-up
    Email            Review
```

---

## ⚙️ Nodes Used

| Node | Purpose |
|---|---|
| **Google Forms Trigger** | Listens for new form submissions in real-time |
| **IF Node** | Routes based on feedback sentiment (positive/negative) |
| **Gmail Node** | Sends automated discount email to the customer |
| **Google Sheets Node** | Logs negative feedback with timestamp for review |

---

## 🚀 How to Use

### Prerequisites
- [n8n](https://n8n.io/) instance (cloud or self-hosted)
- Google account with access to Google Forms, Gmail, and Google Sheets
- n8n Google OAuth2 credentials set up

### Setup Steps

1. **Clone / Import the Workflow**
   - Download the `workflow.json` file from this repository
   - In your n8n instance, go to **Workflows → Import from File**
   - Select the downloaded `workflow.json`

2. **Configure Credentials**
   - Set up **Google OAuth2** credentials in n8n
   - Connect your **Gmail** account
   - Connect your **Google Sheets** account

3. **Set Up Google Form**
   - Create a Google Form with a feedback field
   - Link it to the Google Forms Trigger node in n8n

4. **Configure Google Sheet**
   - Create a Google Sheet for logging negative feedback
   - Update the Google Sheets node with your Sheet ID and range

5. **Customize the Email Template**
   - Edit the Gmail node to customize your discount email content
   - Add your discount code or offer details

6. **Activate the Workflow**
   - Toggle the workflow to **Active** in n8n
   - Test by submitting a form response

---

## 📁 Repository Structure

```
Google-Customer-Feedback-Automation-n8n/
├── workflow.json          # n8n workflow export file (import this into n8n)
├── README.md              # This documentation
└── screenshots/           # Workflow screenshots (optional)
```

---

## 💡 Key Features

- **Fully Automated** — No human intervention needed after setup
- **Smart Conditional Logic** — IF node routes feedback based on content
- **Real-time Processing** — Triggers instantly on form submission
- **Zero Manual Entry** — Google Sheets updated automatically
- **Scalable** — Handles unlimited feedback volume

---

## 🛠️ Tech Stack

- **n8n** — Workflow automation platform
- **Google Forms** — Customer feedback collection
- **Gmail** — Automated discount email delivery
- **Google Sheets** — Negative feedback logging and storage
- **Google OAuth2** — Secure API authentication

---

## 📸 Workflow Preview

*The workflow visual can be seen in the n8n editor after importing `workflow.json`.*

---

## 🤝 About the Author

Built by **[Sameer Faisal](https://www.linkedin.com/in/sameer-faisal-/)** — AI Developer | n8n Automation Specialist | Chatbot Builder

> Open to freelance automation projects. If your team is still manually sorting feedback and sending discount codes — this is exactly what automation is for.

📩 **sameerf737@gmail.com** | [LinkedIn](https://www.linkedin.com/in/sameer-faisal-/) | [GitHub](https://github.com/Sameer051022)

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).
