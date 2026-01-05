# Workflow Export Instructions

## How to export the Guardrails Chatbot workflow:

1. Open your n8n instance at https://stream.nrjay.com
2. Navigate to the workflow "Test - Guardrails Chatbot"
3. Click the "..." menu (three dots) in the top right
4. Select "Download" or "Export"
5. Save the JSON file as `guardrails-chatbot.json` in this directory
6. Delete this instruction file
7. Commit and push the changes

## Alternative: Using n8n API

If you have the n8n API configured, you can export via CLI:

```bash
curl -X GET "https://stream.nrjay.com/api/v1/workflows/m2ei0HJ9L8Iriq5V" \
  -H "X-N8N-API-KEY: YOUR_API_KEY" \
  -o guardrails-chatbot.json
```

## After export:

```bash
git add guardrails-chatbot.json
git commit -m "Add Guardrails Chatbot workflow"
git push origin main
```
