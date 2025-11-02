
# AI-Powered Customer Support Automation

An intelligent customer support automation workflow built with **n8n**, **LangChain**, and **Pinecone**.
It automatically classifies and responds to customer emails using AI, reducing manual workload and improving response speed.

---

<img width="1271" height="599" alt="Image" src="https://github.com/user-attachments/assets/d79d1e28-c368-4351-969e-1fc3e606a2fb" />

## Overview

The client’s support team was spending hours replying to repetitive customer inquiries.
Simple FAQ-related questions consumed the same effort as complex issues, reducing efficiency and delaying responses.

To solve this, I developed a complete **AI-powered email automation system** that classifies incoming messages, generates accurate replies using company policy data, and responds automatically through Gmail.

---

## How It Works

1. **Gmail Trigger:** Detects new customer emails through the Gmail API.
2. **AI Classification:** Uses a LangChain-based classifier to categorize queries as simple or complex.
3. **Automated Replies:**

   * Simple queries are answered using company FAQs stored in a **Pinecone Vector Database**.
   * Responses are generated using **OpenRouter LLMs** and sent automatically through Gmail.
4. **Human Escalation:** Complex queries are skipped for manual review (future feature includes automated human notifications).
5. **Knowledge Base Automation:**
   A secondary workflow monitors Google Docs for updated policy/FAQ documents, generates embeddings via **Ollama**, and updates Pinecone for context-aware AI responses.

---

## Results

* Automated up to **70% of support emails**
* Reduced average response time from **10 minutes to under 1 minute**
* Improved customer satisfaction with faster and consistent replies
* Created a **scalable system** ready for live-support integration

---

## Tech Stack

* **Automation:** n8n
* **AI Models:** OpenRouter (Llama, DeepSeek)
* **Vector Database:** Pinecone
* **Embeddings:** Ollama
* **Integrations:** Gmail API, Google Docs API
* **Language Framework:** LangChain

---

## Workflow Components

| Component             | Description                                  |
| --------------------- | -------------------------------------------- |
| Gmail Trigger         | Detects new customer emails                  |
| Text Classifier       | Categorizes emails as simple or complex      |
| AI Agent              | Generates responses using stored policy data |
| Pinecone Vector Store | Retrieves relevant FAQ information           |
| Ollama Embeddings     | Converts documents into embeddings           |
| Gmail Reply Node      | Sends responses back to customers            |

---

## Setup Instructions

1. **Clone or Download the Repository**

   ```bash
   git clone https://github.com/yourusername/ai-customer-support-automation.git
   cd ai-customer-support-automation
   ```

2. **Import Workflow into n8n**

   * Open your **n8n dashboard**
   * Click **“Import from File”**
   * Upload the file: `Gmail CS Automation.json`

3. **Set Up Required Credentials**

   * **Gmail OAuth2** (for email triggers and replies)
   * **OpenRouter API** (for AI responses)
   * **Pinecone API** (for vector retrieval)
   * **Ollama API** (for embeddings generation)

4. **Configure Variables**

   * Set up Gmail labels or filters if needed
   * Adjust Pinecone namespace (e.g., `FAQ`)
   * Modify system prompt text in the **AI Agent** node to suit your company tone

5. **Activate Workflow**

   * Toggle workflow to “Active” in n8n
   * The automation will now run automatically for each incoming email

---

## Business Impact

This automation enabled the client’s support team to focus on high-priority tickets while AI handled repetitive inquiries, improving both **response quality** and **team productivity**.

---

## Files Included

* `Gmail CS Automation.json` — Full n8n workflow export
* Optional documentation for API setup and credentials (available on request)

---

## Future Enhancements

* Automated team notifications for complex queries
* Integration with live chat or CRM systems
* Performance analytics dashboard


