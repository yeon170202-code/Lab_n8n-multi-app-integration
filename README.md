## 🚀 Workflow Overview

The workflow follows a standard **Source → Transform → Sink** pattern:
1.  **Telegram Trigger:** Listens for incoming messages via a dedicated Telegram Bot.
2.  **Set Node:** Normalizes the JSON payload, mapping nested message data to flat keys.
3.  **Airtable Node:** Creates a new record in a designated base with the mapped information.

## 🛠️ Setup Instructions

1.  **n8n:** Import the `workflow_export.json` into your n8n instance.
2.  **Credentials:** * Create a Telegram Bot via `@BotFather` and add the API Token to n8n.
    * Create an Airtable Personal Access Token (PAT) with `data.records:write` scope.
3.  **Airtable Base:** Create a table with columns for `Sender`, `Message Text`, and `Timestamp`.
4.  **Activate:** Turn the workflow on and send a message to your bot to see it appear in Airtable.

---
*Developed as part of the n8n Automation Course.*
