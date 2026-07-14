# AI-Based Email Classification and Automated Gmail Label Management using n8n

## Workflow Architecture

<img width="1651" height="829" alt="n8n Workflow" src="YOUR_IMAGE_LINK_HERE">

## Project Overview

This project automates Gmail email management using n8n workflow automation. The workflow retrieves emails from Gmail, analyzes the email content, classifies emails into predefined categories, and automatically applies Gmail labels to organize the inbox.

The project demonstrates workflow automation, conditional routing, API integration, and automated email organization to reduce manual effort and improve productivity.

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

The workflow extracts:

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

Keywords related to recruitment, job opportunities, Data Analytics, SQL, Python, Power BI, Business Analyst, Data Engineer, AI Engineer and similar roles are classified as **Job**.

Priority: Medium

**Important Category**

Keywords related to banking, OTP, verification, invoices, tax, passport and healthcare are classified as **Important**.

Priority: High

**Default Category**

Emails that do not match the predefined rules are classified as **Spam**.

Priority: Low

Generated Output

```json
{
  "category": "job",
  "priority": "medium",
  "summary": "Email classified as job"
}



