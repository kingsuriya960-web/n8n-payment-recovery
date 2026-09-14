# n8n Payment Recovery & Dynamic Dunning Workflow

![n8n](https://img.shields.io/badge/n8n-Workflow-FF6D5A?style=for-the-badge&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o-412991?style=for-the-badge&logo=openai&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green.style=for-the-badge)
![Status](https://img.shields.io/badge/Production-Ready-brightgreen?style=for-the-badge)

## 📌 Overview & Business Value
Autonomous payment recovery engine leveraging Stripe Webhooks, AI-powered dunning copy generation via OpenAI GPT-4o, multi-channel outreach (Twilio SMS + SendGrid), Slack billing alerts, and HubSpot CRM status tracking.

### 💡 Primary Use Case
> **E-commerce & SaaS businesses suffering from subscription churn due to failed card charges.**

---

## ⚡ Workflow Visual Architecture
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1100 180" width="100%">
    <defs>
      <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%">
        <stop offset="0%" stop-color="#0f172a"/>
        <stop offset="100%" stop-color="#1e293b"/>
      </linearGradient>
      <marker id="arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#64748b"/>
      </marker>
    </defs>
    <rect width="100%" height="100%" fill="url(#bg)" rx="12"/>
    <text x="20" y="35" fill="#38bdf8" font-family="sans-serif" font-size="16" font-weight="bold">n8n Payment Recovery & Dynamic Dunning Workflow</text>
    
      <g transform="translate(50, 80)">
        <rect width="120" height="50" rx="8" fill="#1e293b" stroke="#3b82f6" stroke-width="2"/>
        <text x="60" y="28" fill="#f8fafc" font-family="sans-serif" font-size="11" font-weight="bold" text-anchor="middle">Stripe Webhook</text>
      </g>
      <path d="M 170 105 L 190 105" stroke="#64748b" stroke-width="2" marker-end="url(#arrow)"/>
    
      <g transform="translate(190, 80)">
        <rect width="120" height="50" rx="8" fill="#1e293b" stroke="#3b82f6" stroke-width="2"/>
        <text x="60" y="28" fill="#f8fafc" font-family="sans-serif" font-size="11" font-weight="bold" text-anchor="middle">Customer Lookup</text>
      </g>
      <path d="M 310 105 L 330 105" stroke="#64748b" stroke-width="2" marker-end="url(#arrow)"/>
    
      <g transform="translate(330, 80)">
        <rect width="120" height="50" rx="8" fill="#1e293b" stroke="#3b82f6" stroke-width="2"/>
        <text x="60" y="28" fill="#f8fafc" font-family="sans-serif" font-size="11" font-weight="bold" text-anchor="middle">Wait 2 Hours</text>
      </g>
      <path d="M 450 105 L 470 105" stroke="#64748b" stroke-width="2" marker-end="url(#arrow)"/>
    
      <g transform="translate(470, 80)">
        <rect width="120" height="50" rx="8" fill="#1e293b" stroke="#3b82f6" stroke-width="2"/>
        <text x="60" y="28" fill="#f8fafc" font-family="sans-serif" font-size="11" font-weight="bold" text-anchor="middle">GPT-4o Dunning</text>
      </g>
      <path d="M 590 105 L 610 105" stroke="#64748b" stroke-width="2" marker-end="url(#arrow)"/>
    
      <g transform="translate(610, 80)">
        <rect width="120" height="50" rx="8" fill="#1e293b" stroke="#3b82f6" stroke-width="2"/>
        <text x="60" y="28" fill="#f8fafc" font-family="sans-serif" font-size="11" font-weight="bold" text-anchor="middle">Twilio / SendGrid</text>
      </g>
      <path d="M 730 105 L 750 105" stroke="#64748b" stroke-width="2" marker-end="url(#arrow)"/>
    
      <g transform="translate(750, 80)">
        <rect width="120" height="50" rx="8" fill="#1e293b" stroke="#3b82f6" stroke-width="2"/>
        <text x="60" y="28" fill="#f8fafc" font-family="sans-serif" font-size="11" font-weight="bold" text-anchor="middle">Slack Alert</text>
      </g>
      <path d="M 870 105 L 890 105" stroke="#64748b" stroke-width="2" marker-end="url(#arrow)"/>
    
      <g transform="translate(890, 80)">
        <rect width="120" height="50" rx="8" fill="#1e293b" stroke="#3b82f6" stroke-width="2"/>
        <text x="60" y="28" fill="#f8fafc" font-family="sans-serif" font-size="11" font-weight="bold" text-anchor="middle">HubSpot Update</text>
      </g>
      
    
  </svg>
```

---

## 🛠️ Architecture & Node Breakdown

| Node Name | Node Type | Function & Logic |
| :--- | :--- | :--- |
| **Stripe Webhook** | `n8n-nodes-base.stripeTrigger` | Stripe Webhook execution step in sequence. |
| **Customer Lookup** | `n8n-nodes-base.stripe` | Customer Lookup execution step in sequence. |
| **Wait 2 Hours** | `n8n-nodes-base.wait` | Wait 2 Hours execution step in sequence. |
| **GPT-4o Dunning** | `n8n-nodes-base.openAi` | GPT-4o Dunning execution step in sequence. |
| **Twilio / SendGrid** | `n8n-nodes-base.twilio` | Twilio / SendGrid execution step in sequence. |
| **Slack Alert** | `n8n-nodes-base.slack` | Slack Alert execution step in sequence. |
| **HubSpot Update** | `n8n-nodes-base.hubspot` | HubSpot Update execution step in sequence. |

---

## 🚀 Quick Setup & n8n Import Instructions

1. **Prerequisites**: Ensure you have a running **n8n instance** (cloud or self-hosted).
2. **Import Workflow**:
   - Open your n8n canvas dashboard.
   - Click **Workflows** → **Import from File**.
   - Select `workflows/payment-recovery.json`.
3. **Configure Credentials**:
   - Open `SETUP.md` to view required API keys and OAuth setups.
   - Bind your credentials to the corresponding nodes.
4. **Activate**:
   - Set the workflow state toggle to **Active**.

---

## 📄 License
This repository is released under the **MIT License**.
