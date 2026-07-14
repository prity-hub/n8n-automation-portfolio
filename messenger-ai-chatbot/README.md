# n8n Automation Portfolio — Sadia Prity

AI chatbots & business automation systems built on n8n.

🎥 Watch the live demo (75s): [https://drive.google.com/file/d/1a3QNN70WqtxvIt1gkaT1K98D2Li2brZr/view?usp=drive_link]

🛒 Hire me on Fiverr: [https://www.fiverr.com/s/VYawZlY]

---

## Featured Project: AI Messenger Chatbot for Business

A production-grade customer service bot for Facebook pages — built for a
clothing shop demo, designed for any service business (salons, clinics,
coaching centers, online stores).

### What it does
- Answers customer questions in Bangla and English from the business's real product/service sheet
- Takes complete orders (name, product, size, quantity, address, phone) → saved to Google Sheets
- Books appointments directly into Google Calendar
- Escalates angry or confused customers to a human — with an instant Telegram alert containing the customer's name and a one-tap link into the conversation
- Sends the owner real-time Telegram alerts for every order and booking
- Full error monitoring: any workflow failure triggers an instant alert

### Architecture
Facebook Webhook → verification (hub challenge) + instant 200 ack → echo/noise
filtering → typing indicator → AI Agent (Gemini, tool-calling) with per-user
session memory → Sheets / Calendar / Graph API tools → reply via Send API.
Separate workflows for error handling and owner notifications
(Sheets-trigger driven).

### Hard problems solved
- Webhook retry storms (duplicate replies) — fixed with immediate acknowledgment
- Echo loops (bot replying to itself) — event filtering
- Per-user session memory scoping
- Prompt-injection and abuse hardening with human handoff
- HTML-safe escaping of user input in notifications

### Files
- [workflow.json](messenger-ai-chatbot/workflow.json) — main bot
- [error-handler.json](messenger-ai-chatbot/error-handler.json) — failure alerts
- [owner-notifications.json](messenger-ai-chatbot/owner-notifications.json) — order/booking/escalation pings
Note: workflow JSONs are sanitized — credentials, IDs, and personal data replaced with placeholders.

---

More projects coming as they reach production quality.
