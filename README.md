# AI-Powered Customer Support Triage

## Project Overview
An AI-powered customer support triage workflow built with n8n. It analyzes incoming support tickets, classifies sentiment and urgency, assigns a priority level, and sends Slack alerts for high-priority tickets.

## Problem Statement
Support teams receive tickets with different urgency levels. Manually identifying critical issues can delay responses to customers who need immediate assistance.

## Solution
This workflow uses an AI Agent with an OpenRouter language model to analyze ticket messages and return structured classifications. High-priority tickets are routed to a designated Slack channel for prompt review.

## Workflow
1. **Webhook:** Receives incoming support tickets through an HTTP POST request.
2. **Input Validation:** Checks that the ticket message is not empty.
3. **AI Agent:** Classifies sentiment, urgency, priority, and the reason for its decision.
4. **Edit Fields:** Extracts the classification results into separate fields.
5. **Priority Check:** Checks whether the ticket priority is High.
6. **Slack Notification:** Sends an alert for high-priority tickets.

## Technologies Used
- n8n — workflow automation
- OpenRouter — AI model access
- AI Agent — ticket classification
- Slack — high-priority notifications
- Webhooks and JSON — data exchange

## Test Results
- **High-priority ticket:** Successfully classified and sent to Slack.
- **Low-priority ticket:** Successfully classified and routed without triggering a Slack alert.

## Security
Credentials and API keys are not included in this repository. Users must configure their own OpenRouter and Slack credentials before running the workflow.

## Setup Instructions
1. Import `workflow.json` into n8n.
2. Configure your own OpenRouter credentials and select a supported model.
3. Connect your own Slack account and choose the destination channel.
4. Configure the Webhook node and test the workflow with sample support tickets.
5. Verify that only high-priority tickets trigger Slack notifications.

## Notes
This project uses OpenRouter rather than the OpenAI node. The workflow is a demonstration and should be tested with representative tickets before production use.
