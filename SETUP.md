# Setup & Credential Guide: n8n Payment Recovery & Dynamic Dunning Workflow

This document details all required API keys, environment variables, and authentication configurations needed to run this n8n automation.

## 🗝️ Required Credentials

| Service / API | Environment Variable / Credential Name | Description |
| :--- | :--- | :--- |
| **STRIPE** | `STRIPE_API_KEY` | Stripe Secret API key for customer & charge verification. |
| **OPENAI** | `OPENAI_API_KEY` | OpenAI API key for generating personalized dunning messaging. |
| **TWILIO** | `TWILIO_ACCOUNT_SID` | Twilio Account SID for SMS dispatch. |
| **TWILIO** | `TWILIO_AUTH_TOKEN` | Twilio Auth Token. |
| **SLACK** | `SLACK_BOT_TOKEN` | Slack Bot Token for posting to #billing-alerts. |
| **HUBSPOT** | `HUBSPOT_ACCESS_TOKEN` | HubSpot Private App Access Token. |

---

## ⚙️ Step-by-Step Configuration

1. **Create API Keys**: Obtain credentials for each service listed above.
2. **Add Credentials in n8n**:
   - Go to **Credentials** in n8n.
   - Add new credentials matching the service types.
3. **Testing**:
   - Execute each node individually to verify payload responses.
   - Trigger the workflow via test payload.
