# Customer Support Ticket Priority Prediction and Automated Assignment System Using Agentforce

## Project Overview

This Salesforce project uses Agentforce and Flow automation to analyze customer support tickets, determine ticket priority, and automate assignment for urgent cases.

The system analyzes the latest support ticket associated with a customer account and determines whether the ticket is:

- High
- Medium
- Low

High-priority tickets trigger automated urgent task creation and are assigned to a senior support agent.

## Salesforce Components

### Custom Object

**Support Ticket Intelligence**

API Name:

`Support_Ticket_Intelligence__c`

### Fields

- Ticket Number
- Customer
- Contact
- Issue Type
- Description
- Priority Level
- Status
- Created Date
- Assigned To
- SLA Breach Risk
- Resolution Time (hrs)

## Automation

### Flow

**Support_Ticket_Intellegence**

The Auto-Launched Flow:

1. Receives the customer Account Name.
2. Retrieves the latest Account.
3. Retrieves the latest Support Ticket associated with that Account.
4. Analyzes the ticket description.
5. Determines the priority.
6. Creates an urgent Task for High-priority tickets.
7. Assigns the ticket to a senior support agent.
8. Returns the final action message.

### Priority Logic

| Priority | Keywords |
|---|---|
| High | urgent, not working, failure |
| Medium | issue, slow, delay |
| Low | No matching priority keywords |

## Agentforce

### Agent

**Support Ticket Priority Analysis**

Developer Name:

`Support_Ticket_Priority_Analysis`

The Agentforce action accepts the customer Account Name and uses the Salesforce Flow to analyze the latest support ticket.

### High Priority Action

For High-priority tickets, the automation creates:

**Task Subject:** `Urgent Ticket Handling`

**Priority:** High

**Status:** Not Started

The task is related to the analyzed support ticket.

## Test Data

**Account:** ABC Technologies

**Contact:** Arun Kumar

**Ticket:** TKT-0001

**Description:**

`Urgent issue: customer application is not working.`

The ticket is identified as High priority and an urgent handling task is created.

## Project Structure

```text
force-app/main/default/
├── aiAuthoringBundles/
├── flows/
└── objects/