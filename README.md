# Healthcare-Customer-Support-Router-Agentic-RAG

In this project, we will leverage the power of AI Agents and RAG Systems to build an intelligent Router Agentic RAG System to handle customer support queries using a custom knowledgebase for a healthcare provider company.

![](https://i.imgur.com/NMz7KjG.png)

### Intelligent Router Agentic RAG System Workflow

This project focuses on building an **Intelligent Router Agentic RAG System** that combines intelligent query analysis, sentiment detection, and dynamic routing with Retrieval-Augmented Generation (RAG) to handle diverse user inquiries efficiently. The workflow includes the following components:

1. **Query Categorization and Sentiment Analysis**:
   - The system uses **OpenAI GPT-4o** to analyze the user's query and determine:
     - **Query Category**: Identifies the type of problem in terms of the best department in the organization which could answer the query, such as billing, appointments, records or insurance
     - **User Sentiment**: Evaluates the user's sentiment (positive, neutral, negative, or distress) to determine if escalation is needed to human support or on-call doctors or automated query resolution using RAG.

2. **Intelligent Routing**:
   - Based on the **query_category** and **query_sentiment**, the system routes the query to the appropriate handling node:
     - **Escalate to Human Support**: If the sentiment is negative, the query is escalated to a human support agent for resolution after the user fills in a form with their details.
     - **Escalate to On-Call Team**: If the sentiment is distress, the query is escalated to the on-call team of doctors for resolution after the user fills in a form with their details.
     - **Generate Department Response**: If the sentiment is positive or neutral, queries related to specific department RAG workflows based on the query category:
       - **Billing Response**: Billing queries are routed to use only billing related documents in the vector database for a specialized response using RAG.
       - **Appointments Response**: Doctor appointment booking related queries are routed to use only appointment related documents in the vector database for a specialized response using RAG.
       - **Records Response**: Patient health records queries are routed to use only records related documents in the vector database for a specialized response using RAG.
       - **Insurance Response**: Health insurance queries are routed to use only insurance related documents in the vector database for a specialized response using RAG.

3. **Knowledge Base Integration (RAG)**:
   - The system integrates with a **Knowledge Base (Vector Database)** to augment responses with relevant and accurate information.
   - Retrieval-Augmented Generation (RAG) ensures that responses are grounded in the latest and most reliable data.

4. **Escalation Mechanism**:
   - Negative sentiment triggers an **escalation to a human support agent**; Distress sentiment triggers an **escalation to an emergency on-call team of doctors** ensuring the user receives empathetic and personalized support for critical issues.
