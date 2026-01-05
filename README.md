# n8n Workflows

Collection of production-ready n8n workflows.

## Workflows

### 1. Guardrails Chatbot

**File:** `guardrails-chatbot.json`

AI-powered chatbot with comprehensive security guardrails to protect against:
- Jailbreak attempts
- PII (Personal Identifiable Information) leakage
- Malicious keywords (hack, exploit, malware, etc.)
- Off-topic requests
- NSFW content

**Features:**
- Input validation with multiple guardrail layers
- Output sanitization (PII removal)
- User-friendly error messages explaining why requests were blocked
- Transparent reporting of triggered guardrails
- Topical alignment enforcement (software development/tech scope)

**Tech Stack:**
- n8n Webhook Trigger
- Langchain Guardrails (Input & Output)
- AI Agent with OpenRouter/Gemini 2.0 Flash
- Custom response formatting

**Guardrails Configuration:**

*Input Guardrails:*
- Jailbreak Detection (threshold: 0.7)
- PII Detection (all types)
- Keywords Blocking
- NSFW Detection (threshold: 0.7)
- Topical Alignment (threshold: 0.7)

*Output Guardrails:*
- PII Sanitization

**API Response Format:**

Blocked request:
```json
{
  "blocked": true,
  "response": "Ihre Anfrage wurde von unseren Sicherheitsrichtlinien blockiert (Gründe: jailbreak, nsfw). Bitte stellen Sie sicher, dass Ihre Anfrage sich auf Software-Entwicklung, Programmierung und Technologie bezieht..."
}
```

Valid request:
```json
{
  "blocked": false,
  "response": "AI-generated response here..."
}
```

## Installation

1. Import the workflow JSON file into your n8n instance
2. Configure your OpenRouter API credentials
3. Activate the workflow
4. Test with the webhook endpoint

## License

MIT
