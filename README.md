# 🎙️ AI Voice Assistant — n8n + Gemini + Telegram

Autonomer KI-Assistent, gesteuert über Telegram-Sprachnachrichten. Sprich einen Befehl, der Agent erledigt den Rest.

## Was er kann

- 📅 **Termine erstellen** — „Teammeeting morgen um 15 Uhr" → Google Calendar Event
- 📧 **E-Mail-Entwürfe** — „Schreib eine Mail an Max wegen dem Meeting" → Gmail Draft
- ✅ **To-Dos erfassen** — „Erinnere mich an den Bericht bis Freitag"

## Tech Stack

- **n8n** — Workflow Engine (Self-Hosted, Docker)
- **Google Gemini 2.5 Flash** — Audio-Transkription + AI Agent
- **Telegram Bot API** — Webhook-basierter Trigger
- **Google Calendar API + Gmail API** — Tool-Ausführung via Function Calling

## Wie es funktioniert

```
Telegram Voice Message
→ Audio Download (Telegram API)
→ Base64 Konvertierung
→ Gemini Transkription (multimodal, kein separater Whisper-Schritt)
→ AI Agent (Intent Recognition + autonomes Tool Selection)
→ Google Calendar / Gmail
→ Bestätigung zurück in Telegram
