# AI-Based Email Classification and Automated Gmail Label Management using n8n

## Workflow Architecture

<img width="1651" height="829" alt="n8n Workflow" src="https://github.com/user-attachments/assets/f66e1587-3cb0-416e-8320-001e2acb1a74" />

## Project Overview

This project automates Gmail email management using n8n workflow automation. The workflow retrieves emails from Gmail, analyzes the email content, classifies emails into predefined categories, and automatically applies Gmail labels to organize the inbox.

The project demonstrates workflow automation, API integration, conditional routing, and automated email organization to reduce manual effort and improve productivity.

## Project Objectives

- Automate Gmail email processing.
- Retrieve email details automatically from Gmail.
- Classify emails into Important, Job, and Spam categories.
- Automatically apply Gmail labels based on the detected category.
- Improve email organization and productivity.
- Build an automated email management workflow using n8n.

## Tools and Technologies

| Tool | Purpose |
|------|---------|
| n8n | Workflow Automation |
| Gmail API | Retrieve and Update Gmail Messages |
| Switch Node | Conditional Routing |
| Edit Fields Node | Data Preparation |
| Gmail Labels | Automatic Email Organization |
| GitHub | Version Control |

## Workflow Explanation

### Manual Trigger

Starts the workflow manually when the user clicks **Execute Workflow**.

### Gmail – Get Many Messages

Retrieves multiple emails from the Gmail inbox.

The workflow extracts the following information:

- Email ID
- Thread ID
- Sender
- Receiver
- Subject
- Email Content
- Existing Labels

### Email Classification

The workflow analyzes the email content and classifies emails using predefined business rules.

**Job Category**

Emails containing keywords related to recruitment, job opportunities, Data Analytics, SQL, Python, Power BI, Business Analyst, Data Engineer, AI Engineer, Excel and similar roles are classified as **Job**.

**Priority:** Medium

**Important Category**

Emails containing keywords related to banking, OTP, verification, invoices, tax, passport, healthcare and similar important notifications are classified as **Important**.

**Priority:** High

**Default Category**

Emails that do not match the predefined rules are classified as **Spam**.

**Priority:** Low

### Generated Output

```json
{
  "category": "job",
  "priority": "medium",
  "summary": "Email classified as job"
}
```

### Switch Node

Routes emails to the appropriate branch based on the generated category.

| Category | Output Branch |
|----------|---------------|
| Important | Important Branch |
| Job | Job Branch |
| Spam | Spam Branch |

### Edit Fields

Each branch prepares the required email information before updating Gmail labels.

- Important → Edit Fields
- Job → Edit Fields 1
- Spam → Edit Fields 2

### Gmail Label Management

Automatically applies Gmail labels based on the classified category.

| Category | Gmail Label |
|----------|-------------|
| Important | Important |
| Job | Job |
| Spam | AI-Spam |

## Sample Output

| Email Type | Category | Gmail Label |
|------------|----------|-------------|
| Recruiter Email | Job | Job |
| Bank Notification | Important | Important |
| Promotional Email | Spam | AI-Spam |

## Key Features

- Automated Gmail email processing
- Email classification using predefined business rules
- Automatic Gmail label assignment
- Conditional routing using Switch Node
- Batch processing of multiple emails
- Workflow automation using n8n
- Gmail inbox organization

## Business Benefits

- Reduces manual email sorting.
- Organizes Gmail inbox automatically.
- Prioritizes important emails.
- Separates recruitment emails for easy tracking.
- Improves productivity through workflow automation.

## Future Enhancements

- Integrate Google Gemini or OpenAI for AI-powered email classification.
- Replace keyword-based classification with Natural Language Processing (NLP).
- Store classified email data in Google Sheets.
- Develop an interactive dashboard for email analytics.
- Schedule automatic workflow execution using Gmail Trigger.


## 👤 Author

Rekaa
📊 Aspiring Data Analyst
🚀 Open to opportunities


