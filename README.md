# AI Laptop Customer Support Agent

An AI-powered customer support automation system that understands customer laptop requirements, searches a PostgreSQL inventory, and automatically responds to customers through Gmail.

## Project Overview

This project automates laptop recommendations using Generative AI, n8n workflow automation, and PostgreSQL.

Customers can send natural-language emails describing their laptop requirements. The AI extracts structured information such as budget, RAM, storage, and brand preferences. The system then searches the laptop inventory and generates a relevant response.

## Key Features

- **Natural Language Understanding:** Extracts laptop requirements from customer emails using an LLM.
- **Requirement Extraction:** Identifies budget, RAM, storage, brand, and use case.
- **Data Normalization:** Converts customer requirements into structured database filters using JavaScript.
- **Database Integration:** Searches laptop inventory stored in PostgreSQL.
- **Dynamic SQL Queries:** Filters products according to customer requirements.
- **Automated Email Responses:** Sends personalized laptop recommendations through Gmail.
- **Dataset Processing:** Imports and transforms laptop inventory data into database records.

## Technology Stack

| Component | Technology |
|---|---|
| Workflow Automation | n8n |
| LLM | OpenAI GPT-5-mini |
| Database | PostgreSQL (Neon) |
| Programming | JavaScript |
| Email Integration | Gmail |
| Data Processing | CSV |
| AI Component | n8n Information Extractor |

## System Architecture

```text
Customer Email
      |
      v
Gmail Trigger
      |
      v
Information Extractor
      |
      v
OpenAI LLM
      |
      v
Requirement Normalization
      |
      v
PostgreSQL Query
      |
      v
Laptop Inventory
      |
      v
Response Generation
      |
      v
Gmail Reply
```

### Data Ingestion Pipeline

```text
Laptop CSV Dataset
       |
       v
HTTP Request
       |
       v
Extract from File
       |
       v
JavaScript Data Cleaning
       |
       v
PostgreSQL
```

## How It Works

1. A customer sends an email describing their laptop requirements.
2. Gmail Trigger detects the incoming email.
3. The Information Extractor uses an OpenAI model to identify structured requirements.
4. JavaScript normalizes the extracted values into database-friendly parameters.
5. PostgreSQL executes a query against the laptop inventory.
6. JavaScript processes the matching records and prepares a customer-friendly response.
7. Gmail sends the recommendation to the customer.

## Example Customer Request

"I need a laptop under ₹80,000 with at least 16GB RAM and 1TB SSD."

The system extracts requirements such as:

- Maximum budget: ₹80,000
- Minimum RAM: 16GB
- Minimum storage: 1TB

It then searches the database for matching laptops and generates an email response.

## Database

The project uses PostgreSQL hosted on Neon to store and query laptop inventory.

The database supports filtering based on:

- Product name
- Price
- RAM capacity
- Storage capacity
- Processor
- Operating system

## Project Structure

```text
ai-laptop-customer-support-agent/
│
├── README.md
├── sharmila0512-workflows/
│   └── ULM8CoYzO5WOvJ5Z-AI_Laptop_Customer_Support.json
│
└── docs/
    └── architecture.png
```

## Setup Requirements

- n8n instance
- OpenAI API credentials
- PostgreSQL database (Neon)
- Gmail OAuth2 credentials
- Laptop inventory CSV dataset

Import the workflow JSON into n8n and configure your own credentials and PostgreSQL database before execution.

**Security:** Never publish API keys, OAuth tokens, database passwords, or private customer information.

## Engineering Concepts Demonstrated

- LLM-based information extraction
- Prompt engineering
- Structured output processing
- JavaScript data transformation
- Relational database integration
- Dynamic SQL querying
- Workflow orchestration
- Automated email communication
- AI-powered business process automation

## Author

**Sharmila Abdulrazak**

AI & Data Science | AI/ML Engineering | Generative AI

GitHub: https://github.com/Sharmila2112

---

*Built as an AI-powered automation project to demonstrate practical applications of LLMs, workflow orchestration, and database-driven decision-making.*
