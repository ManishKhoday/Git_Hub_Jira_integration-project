# 🚀 Automate JIRA Issue Creation from GitHub Webhook with Python 🐍

## 🌟 Overview

This project demonstrates how to automate the creation of JIRA issues directly from GitHub events using Python. It bridges the gap between development and QA, streamlining bug tracking and issue management. When a developer validates a bug reported on GitHub, a corresponding JIRA ticket is automatically created, saving time and ensuring no valid issue is missed.

## 🎯 Problem Statement

QA engineers and other team members report bugs as issues on GitHub. Developers must triage these issues to determine validity. Valid issues then require manual JIRA ticket creation, a time-consuming process.

## ✅ Solution

We use a Python application to listen for specific GitHub events (e.g., a comment containing "/jira") and automatically create a JIRA ticket with the relevant information.

### ⚙️ Tech Stack
*   **Python:** The core language for the automation script.
*   **Flask:** To create a web application that acts as a webhook endpoint.
*   **JIRA API:** To programmatically create issues in JIRA.
*   **GitHub Webhooks:** To trigger the Python application upon specific events.
*   **requests library:** To make API calls.

### 🏗️ Architecture

1.  **GitHub Webhook:** Configured to trigger on specific comments (e.g., "/jira") on GitHub issues.
2.  **Python/Flask Application:**
    *   Receives the issue details from the GitHub webhook in JSON format.
    *   Parses the JSON data to extract relevant information (e.g., description, reporter).
    *   Uses the JIRA API to create a new ticket with the extracted information.
3.  **JIRA:** A new ticket is created with all the relevant information pulled from the github issue.

## 🚀 Setup

### Prerequisites

*   **JIRA Account:** You'll need a JIRA account with API access.
*   **Python 3.6+:** Make sure you have Python installed.
*   **Flask:** Install using pip: `pip install flask`
*   **requests:** Install using pip: `pip install requests`

### 1. JIRA Setup

1.  Set up a free JIRA account (if you don't have one).
2.  Generate an API token for your JIRA account. You will need this to authenticate your requests to the JIRA API.

### 2. Python Script (Flask App)


### 3. GitHub Webhook Configuration

1.  Go to your GitHub repository settings.
2.  Click on "Webhooks" and then "Add webhook".
3.  **Payload URL:** Enter the URL of your Flask application (e.g., `https://your-ec2-instance/webhook`).
4.  **Content type:** `application/json`.
5.  **Secret:** (Optional, but recommended) Set a secret to secure your webhook.
6.  **Which events would you like to trigger this webhook?** Choose "Specific issues" and select "Issue comments".
7.  Make sure the webhook is active.




## 🧪 Testing

1.  Create an issue on your GitHub repository.
2.  Add a comment containing "/jira".
3.  Check your JIRA project to see if a new ticket has been created.

## 🚀 Deployment

1.  **EC2 Instance:** Launch an EC2 instance or any suitable server.
2.  **Deploy Flask App:** Deploy your Flask application to the server.
3.  **Configure Webhook:**  Update the GitHub webhook with the correct URL of your deployed application.