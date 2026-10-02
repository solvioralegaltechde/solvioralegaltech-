# Telegram Bridge & Approval Configuration (Solviora)

## Integration Overview
This document defines the technical link between the Solviora autonomous agent ecosystem and Miguel's mobile command center via Telegram.

## Bot Credentials & Endpoints
* **Bot Name:** Solviora Assistant
* **Username:** `@Solviora_assistant_bot`
* **API Base URL:** `https://api.telegram.org/bot8637242309:AAGp6k7n13wax4cAzTjBEDeVTFKcYDxyW28/`

## Automated Approval Protocol (Human-in-the-Loop)
1. **Payload Generation:** When the Social Media or Chief of Staff agent completes a post package, it structures the content (carousel text, caption, visual theme).
2. **Webhook Dispatch:** The automation bridge (e.g., Make.com) sends an HTTP POST request to the Telegram API (`sendMessage`) targeting Miguel's chat ID.
3. **Actionable Response:** 
   - The message displays the content preview and compliance check.
   - Miguel replies with **"OK"** or a thumbs-up emoji to trigger immediate automated publishing to Instagram.
