# 📧 AI-Based Email Classification and Automated Gmail Label Management using n8n

## 📷 Workflow Architecture

<p align="center">
  <img src="images/workflow.png" alt="AI Email Classification Workflow" width="1000">
</p>

---

## 📌 Project Overview

This project automates Gmail email management using **n8n workflow automation**. The workflow retrieves emails from Gmail, analyzes the email content using JavaScript-based classification logic, categorizes emails into different groups, and automatically applies Gmail labels based on the detected category.

The main objective of this project is to reduce manual email sorting, improve inbox organization, and automate Gmail label management using workflow automation.

---

## 🎯 Project Objectives

* Automate Gmail email processing.
* Retrieve email details automatically from Gmail.
* Classify emails into three categories:

  * Important
  * Job
  * Spam
* Automatically apply Gmail labels based on the detected category.
* Improve email organization and user productivity.
* Build an intelligent workflow using n8n automation.

---

## 🛠️ Tools & Technologies Used

| Tool             | Purpose                      |
| ---------------- | ---------------------------- |
| n8n              | Workflow Automation          |
| Gmail API        | Retrieve Gmail Messages      |
| JavaScript       | Email Classification Logic   |
| Switch Node      | Conditional Routing          |
| Edit Fields Node | Prepare Data Before Labeling |
| Gmail Label API  | Apply Gmail Labels           |
| GitHub           | Version Control              |

---

# 🔄 Workflow Architecture

```text
Manual Trigger
      │
      ▼
Get Many Gmail Messages
      │
      ▼
JavaScript Code
(Classify Email)
      │
      ▼
Switch Node
 ┌──────────┬──────────┬──────────┐
 │          │          │
 ▼          ▼          ▼
Important   Job       Spam
 │          │          │
 ▼          ▼          ▼
Edit Fields Edit Fields Edit Fields
 │          │          │
 ▼          ▼          ▼
Add Label   Add Label   Add Label
```

---

# ⚙️ Workflow Explanation

## Step 1 – Manual Trigger

**Purpose**

Starts the workflow manually whenever the user clicks **Execute Workflow**.

---

## Step 2 – Gmail Node (Get Many Messages)

**Purpose**

Retrieves multiple emails from the Gmail inbox.

### Email Details Retrieved

* Email ID
* Thread ID
* Sender
* Receiver
* Subject
* Email Body
* Labels

Example:

**From**

Job Hai

**Subject**

Fresh jobs picked for you

---

## Step 3 – JavaScript Code Node

**Purpose**

Analyzes the email content and classifies each email using keyword-based logic.

### Job Email Keywords

* Data Analytics
* Business Analyst
* SQL
* Python
* Power BI
* Machine Learning
* AI Engineer
* Data Engineer
* Excel

Output

* Category → Job
* Priority → Medium

---

### Important Email Keywords

* Bank
* OTP
* Invoice
* Verification
* Passport
* Tax
* Healthcare

Output

* Category → Important
* Priority → High

---

### Default Category

If no matching keywords are found:

* Category → Spam
* Priority → Low

---

### Generated Output

```json
{
  "category": "job",
  "priority": "medium",
  "summary": "Email classified as job"
}
```

---

## Step 4 – Switch Node

**Purpose**

Routes emails to different branches based on the generated category.

### Routing Rules

| Category  | Branch           |
| --------- | ---------------- |
| Important | Important Branch |
| Job       | Job Branch       |
| Spam      | Spam Branch      |

---

## Step 5 – Edit Fields Nodes

Each category has its own **Edit Fields** node to prepare the required email information before applying Gmail labels.

| Branch    | Node          |
| --------- | ------------- |
| Important | Edit Fields   |
| Job       | Edit Fields 1 |
| Spam      | Edit Fields 2 |

---

## Step 6 – Gmail Add Label to Message

Automatically applies Gmail labels based on the classified category.

| Category  | Gmail Label |
| --------- | ----------- |
| Important | Important   |
| Job       | Job         |
| Spam      | AI-Spam     |

---

# 📊 Sample Workflow Output

| Email             | Category  | Label Applied |
| ----------------- | --------- | ------------- |
| Recruiter Email   | Job       | Job           |
| Bank Notification | Important | Important     |
| Promotional Email | Spam      | AI-Spam       |

---

# ✅ Key Features

* Automated Gmail email processing
* Keyword-based email classification
* Automatic Gmail label assignment
* Conditional routing using Switch Node
* Multiple email processing
* Structured workflow automation
* Easy to extend with AI models

---

# 📈 Business Benefits

* Eliminates manual email sorting.
* Improves Gmail inbox organization.
* Automatically prioritizes important emails.
* Helps users quickly identify job-related emails.
* Reduces time spent managing emails.
* Demonstrates business workflow automation using n8n.

---

# 🚀 Future Enhancements

* Integrate Google Gemini or OpenAI for AI-powered email classification.
* Replace keyword-based logic with Natural Language Processing (NLP).
* Automatically generate email replies.
* Store classified email data in Google Sheets or a database.
* Build an analytics dashboard showing:

  * Job Emails
  * Important Emails
  * Spam Emails
* Schedule automatic execution using Gmail Trigger.

---

# 📂 Repository Structure

```text
AI-Email-Classification-n8n/
│
├── images/
│   └── workflow.png
│
├── workflow/
│   └── email-classification-workflow.json
│
├── README.md
│
└── LICENSE
```


# 👩‍💻 Author

**Rekaa Selvaraj**

Aspiring Data Analyst | AI-Driven Data Analytics | n8n Workflow Automation | Python | SQL | Power BI | GitHub


