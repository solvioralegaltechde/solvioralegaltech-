# Autonomous Publishing & Approval Architecture (Solviora)

## Role & Purpose
This document defines the 24/7 automated pipeline for **Solviora**, ensuring that social media content (Instagram carrossels, infographics, and insights) flows seamlessly from AI generation to human approval and final publishing, without manual text creation.

## The Human-in-the-Loop Pipeline
1. **Autonomous Generation:** 
   - The *Social Media & Content Agent* generates posts according to a structured format (Visual Concept + Caption + Mandatory LegalTech Compliance Disclaimer).
   - Content adheres strictly to the dark-mode visual identity (deep blue-grey backgrounds, pure white typography, vivid yellow `#FFC800` accents).
2. **Delivery & Notification:**
   - Automation bridges (such as Make.com via webhooks) capture the generated payload.
   - A notification is instantly sent to Miguel's mobile device (via Telegram or secure channel) displaying the slide text and caption.
3. **The Single-Click Approval ("OK"):**
   - Miguel reviews the preview.
   - Clicking **[OK / Approve]** triggers the downstream publishing sequence.
4. **Automated Publishing:**
   - The approved payload is sent directly to the official Instagram Graph API.
   - The post goes live automatically, maintaining 24/7 channel presence without manual web dashboard logins.

## Technical Payload Structure for Automation
Every automated post output generated for the webhook/API bridge must follow this JSON-like structure:
```json
{
  "platform": "instagram",
  "format": "carousel",
  "visual_theme": "dark_mode_yellow_accents",
  "slides": [
    {"slide_number": 1, "text": "...", "design_note": "..."},
    {"slide_number": 2, "text": "...", "design_note": "..."}
  ],
  "caption": "...",
  "compliance_check": "passed_legaltech_no_legal_advice",
  "status": "pending_approval"
}
