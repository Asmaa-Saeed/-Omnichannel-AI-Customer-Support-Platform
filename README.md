# 🤖 Omnichannel AI Customer Support Platform

> An enterprise-grade AI automation platform that enables businesses to automate customer support across multiple communication channels while seamlessly integrating AI agents, human support, and a continuously evolving knowledge base.

<p align="center">

![Status](https://img.shields.io/badge/Status-Production-success)
![Automation](https://img.shields.io/badge/Built%20With-n8n-FF6D5A)
![Backend](https://img.shields.io/badge/Flask-REST_API-black)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-412991)
![Database](https://img.shields.io/badge/PostgreSQL-336791)
![VectorDB](https://img.shields.io/badge/Supabase-VectorDB-3ECF8E)

</p>

---

# 📖 Overview

This repository showcases the **AI automation layer** of a production-ready omnichannel customer support platform designed to automate customer interactions while enabling seamless collaboration between AI assistants and human support teams.

Customers can communicate through multiple channels—including **Website, WhatsApp, Instagram, Facebook Messenger, and Mobile Application**—while all conversations are managed from a centralized support dashboard.

The automation layer integrates **LLMs**, **Retrieval-Augmented Generation (RAG)**, **workflow automation**, **REST APIs**, and **vector search** to deliver accurate, context-aware responses and continuously improve the AI knowledge base.

As the **AI Automation Engineer**, my role focused on designing and implementing the automation infrastructure using **n8n**, **Flask**, **OpenAI APIs**, **Supabase Vector Store**, and **PostgreSQL**, connecting frontend interactions with backend services and AI workflows.

---

# 🎯 Business Problem

Modern businesses receive customer inquiries from multiple communication channels, making it difficult to:

- Maintain consistent responses across platforms.
- Route conversations between AI and human agents.
- Keep the AI knowledge base up to date.
- Manage customer conversations from a single interface.
- Continuously improve AI performance based on real customer interactions.

Traditional chatbot solutions often rely on static FAQs and lack an efficient feedback loop for learning from unanswered questions.

---

# 💡 Solution

This platform provides an end-to-end AI-powered customer support solution that combines intelligent automation with human collaboration.

The automation layer:

- Receives customer messages from multiple channels.
- Retrieves relevant business knowledge using RAG.
- Generates context-aware responses with OpenAI.
- Transfers conversations to human agents when necessary.
- Logs unanswered questions for administrator review.
- Automatically updates the knowledge base through embedding workflows.
- Centralizes customer conversations in a unified dashboard.

The result is a scalable support platform that continuously improves over time while reducing repetitive manual work.

---

# 🏗 System Architecture

The platform is built around a centralized AI automation layer that connects customer communication channels, backend services, AI models, human support agents, and the company's knowledge base.

Each customer request follows an automated workflow that determines whether the AI can resolve the inquiry or whether the conversation should be escalated to a human support agent.

```text
                      Customer Channels

 Website • WhatsApp • Instagram • Facebook • Mobile App

                               │
                               ▼

                      Flask REST APIs

                               │
                               ▼

                    n8n Automation Engine

        ┌────────────────┬─────────────────┬─────────────────┐
        ▼                ▼                 ▼

 AI Conversation    Human Handoff     Background Jobs

        │                │                 │
        └────────────────┼─────────────────┘
                         ▼

               OpenAI GPT-4o-mini

                         │
                         ▼

              RAG Knowledge Retrieval

                         │
                ┌────────┴────────┐
                ▼                 ▼

          PostgreSQL      Supabase Vector Store

                         │
                         ▼

                 Admin Dashboard
```

> Replace the diagram above with your architecture image.

```text
images/architecture.png
```

---

# 🧩 Core Components

The platform consists of several independent automation components working together to deliver a seamless customer support experience.

| Component | Purpose |
|----------|---------|
| 🤖 AI Conversation Engine | Handles customer conversations using OpenAI and RAG. |
| 📚 Knowledge Base (RAG) | Retrieves relevant business information from the vector database before generating responses. |
| 👨‍💻 Human Handoff | Transfers conversations to human agents when AI cannot resolve the request. |
| 🧠 Continuous Learning | Captures unanswered questions and updates the knowledge base after administrator approval. |
| ⭐ Customer Rating | Sends automatic satisfaction surveys after conversations are resolved. |
| 🔔 Admin Notifications | Triggers internal notifications for important workflow events. |
| 🌍 Omnichannel Integration | Connects Website, WhatsApp, Instagram, Facebook, and Mobile App into a unified support experience. |

---

# 👩‍💻 My Contribution

As the **AI Automation Engineer**, I was responsible for designing and implementing the automation layer that powers the platform.

### My responsibilities included:

- Designing and building automation workflows using **n8n**
- Developing **Flask REST APIs** for workflow integration
- Connecting frontend actions with backend automation
- Integrating OpenAI APIs
- Building Retrieval-Augmented Generation (RAG) pipelines
- Integrating Supabase Vector Store
- Implementing Human Handoff workflows
- Developing Knowledge Base training workflows
- Creating reusable webhook-based integrations
- Managing conversation routing and workflow orchestration
- Implementing logging, validation, and error handling

> My contribution focused on the AI automation and integration layer. The frontend application and core backend business logic were developed collaboratively by other members of the team.

---

# ⚙️ Automation Workflows

The following workflows represent the core automation systems I designed and implemented as part of the platform's AI automation layer. Together, they automate customer interactions, enable seamless collaboration between AI and human agents, and continuously improve the platform's knowledge base.

---

## 🤖 AI Conversation Workflow

### Purpose

Processes incoming customer messages, retrieves relevant knowledge from the RAG system, generates context-aware AI responses using OpenAI, and returns the response through the original communication channel.

### Workflow

```text
Customer Message
        │
        ▼
Communication Channel
        │
        ▼
Flask REST API
        │
        ▼
n8n Workflow
        │
        ├── Validate Request
        ├── Retrieve Conversation History
        ├── Search Knowledge Base (RAG)
        ├── Build AI Prompt
        ├── Generate AI Response
        └── Send Response
```

### Technologies

- n8n
- Flask
- OpenAI API
- PostgreSQL
- Supabase Vector Store

### Demo

🎥 `videos/ai-conversation-demo.mp4`

---

## 👨‍💻 Human Handoff Workflow

### Purpose

Enables seamless transition from AI support to a human agent whenever the customer requests human assistance or the AI is unable to confidently resolve the inquiry.

The complete conversation history remains available to support agents through the admin dashboard.

### Workflow

```text
Customer Message
        │
        ▼
AI Assistant
        │
        ▼
Human Support Requested
        │
        ▼
Assign Conversation
        │
        ▼
Support Dashboard
        │
        ▼
Agent Responds
        │
        ▼
Issue Resolved
        │
        ▼
Dashboard Action
        │
        ▼
Flask Endpoint
        │
        ▼
n8n Workflow
        │
        ▼
Conversation Status Updated
```

### Technologies

- n8n
- Flask
- PostgreSQL
- REST APIs

### Demo

🎥 `videos/human-handoff-demo.mp4`

---

## 🧠 Knowledge Base Training (Missed Questions)

### Purpose

Continuously improves the AI assistant by capturing unanswered customer questions, allowing administrators to review them, provide verified answers, and automatically synchronize the approved knowledge with the RAG system.

Instead of retraining the language model, the workflow updates the vector database by generating new embeddings, enabling the assistant to answer similar questions in future conversations.

### Workflow

```text
Customer Question
        │
        ▼
AI Cannot Answer
        │
        ▼
Question Logged
        │
        ▼
Admin Review Dashboard
        │
        ▼
Administrator Adds Answer
        │
        ▼
Flask API
        │
        ▼
n8n Workflow
        │
 ┌──────┼─────────────┐
 │      │             │
 ▼      ▼             ▼
Create  Update     Delete
 │      │             │
 └──────┼─────────────┘
        ▼
Generate Embeddings
        │
        ▼
Supabase Vector Store
        │
        ▼
Knowledge Base Updated
```

### Supported Operations

| Operation | Description |
|-----------|-------------|
| ➕ Create | Store newly approved knowledge in the vector database. |
| ✏️ Update | Remove outdated embeddings and generate updated ones. |
| 🗑 Delete | Remove obsolete knowledge from the knowledge base. |

### Technologies

- n8n
- Flask
- OpenAI Embeddings
- PostgreSQL
- Supabase Vector Store

### Demo

🎥 `videos/missed-questions-demo.mp4`

---

## ⭐ Customer Rating Workflow

### Purpose

Automatically collects customer feedback after conversations are resolved, helping the business measure customer satisfaction and service quality.

### Workflow

```text
Conversation Resolved
        │
        ▼
Trigger Survey
        │
        ▼
Customer Rating
        │
        ▼
Store Feedback
        │
        ▼
Dashboard Analytics
```

### Technologies

- n8n
- Flask
- PostgreSQL

# 📸 Visual Showcase

The following screenshots and demo videos highlight the core automation workflows and user interface of the platform.

---

## 🏗 System Architecture

📷 High-level architecture of the platform.

![Architecture](images/architecture.png)

---

## 🤖 AI Conversation

Demonstrates how customer messages are processed through the AI automation pipeline.

🎥 Demo

https://github.com/user-attachments/...

---

## 👨‍💻 Human Handoff

Shows how conversations are seamlessly transferred from the AI assistant to a human support agent.

📷 Dashboard

![Human Handoff](images/handoff-dashboard.png)

🎥 Demo

https://github.com/user-attachments/...

---

## 🧠 Knowledge Base Training (Missed Questions)

Illustrates the workflow used to review unanswered questions and automatically synchronize approved answers with the RAG knowledge base.

📷 Admin Review Queue

![Missed Questions](images/missed-questions.png)

🎥 Demo

https://github.com/user-attachments/...

---

## ⭐ Customer Rating

Displays the automated customer satisfaction survey triggered after conversation resolution.

🎥 Demo

https://github.com/user-attachments/...

---

## 🖥 Admin Dashboard

Overview of the centralized dashboard used by support agents to monitor conversations, manage AI interactions, and review customer requests.

![Dashboard](images/dashboard.png)



# ⚡ Engineering Challenges

Building a production-ready omnichannel AI support platform required solving several engineering challenges related to workflow orchestration, API integration, conversation management, and knowledge synchronization.

---

## 🔄 Backend Integration

One of the primary challenges was connecting frontend actions with automation workflows.

To address this, I developed Flask REST APIs that act as the communication layer between the dashboard and n8n workflows, ensuring secure and reliable workflow execution.

---

## 🌍 Omnichannel Synchronization

Supporting multiple communication channels while maintaining a unified customer experience required consistent conversation routing and state management.

The automation layer was designed to process requests from different channels while keeping conversations centralized within a single dashboard.

---

## 👨‍💻 Human Handoff

Designing a seamless transition between AI and human support without losing conversation context was a key challenge.

The workflow preserves conversation history, enables manual intervention through the dashboard, and allows automation to resume after the issue is resolved.

---

## 📚 Knowledge Base Synchronization

Keeping the RAG knowledge base continuously updated without interrupting the customer experience required a dedicated automation workflow.

A review process was implemented where unanswered questions are validated by administrators before new embeddings are generated and synchronized with the vector database.

---

## 🔗 Workflow Orchestration

The platform consists of multiple independent workflows that communicate through REST APIs and webhooks.

Designing these workflows to operate reliably while exchanging data between services required careful orchestration and state management.

---

## 🛡 Reliability & Error Handling

To improve production stability, the automation layer includes:

- Request validation
- Workflow logging
- Error handling
- Retry mechanisms
- API response validation

These measures help ensure reliable execution across different automation workflows.

---


# 🛠 Tech Stack

| Category | Technologies |
|----------|--------------|
| **Automation** | n8n |
| **Backend** | Flask, Python |
| **AI** | OpenAI API, GPT-4o-mini |
| **Knowledge Base** | RAG, Supabase Vector Store |
| **Database** | PostgreSQL |
| **Integration** | REST APIs, Webhooks |
| **Development** | JavaScript, Python |

---

# 📸 Visual Showcase

The following screenshots and demo videos highlight the platform's core workflows and user experience.

## 🏗 System Architecture

📷 Architecture Diagram

---

## 🤖 AI Conversation

🎥 AI conversation workflow demo

---

## 👨‍💻 Human Handoff

📷 Dashboard Screenshot

🎥 Human handoff demo

---

## 🧠 Knowledge Base Training (Missed Questions)

📷 Admin Review Queue

🎥 Knowledge base training demo

---

## ⭐ Customer Rating

🎥 Customer satisfaction workflow demo

---

## 🖥 Admin Dashboard

📷 Dashboard Overview

---

# 🔒 Security & Privacy

This repository showcases the platform's automation architecture and engineering approach while respecting client confidentiality.

To protect proprietary business logic, the following assets are intentionally excluded:

- Production n8n workflows
- API credentials
- Internal prompts
- Database schema
- Customer data
- Business-specific logic
- Environment configuration

The repository focuses on the overall architecture, workflow design, and technical implementation without exposing sensitive information.

---



# 🚀 Future Improvements

Potential future enhancements include:

- Multi-agent orchestration
- Voice AI integration
- Sentiment analysis
- Automated knowledge validation
- AI quality evaluation
- Analytics dashboard
- Advanced workflow monitoring

---

# 👩‍💻 Author

**Asmaa Saeed**

**AI Automation Engineer**

Specialized in:

- AI Automation
- AI Agents
- Workflow Automation
- n8n
- Flask
- Python
- REST APIs
- OpenAI API
- RAG Systems
- Supabase
- PostgreSQL
