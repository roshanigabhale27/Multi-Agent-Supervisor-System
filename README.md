# Multi-Agent-Supervisor-System
A Multi-Agent AI System built with n8n demonstrating Single-Agent vs Multi-Agent architectures, Supervisor-Worker pattern, agent messaging, task delegation, and tool integration.

## Overview

This project demonstrates the difference between Single-Agent and Multi-Agent Systems using n8n.

The workflow follows the Supervisor–Worker pattern, where a Supervisor Agent delegates tasks to specialized Worker Agents. Each agent performs a specific role, and the final result is combined and returned to the user.

---

## Objective

Build a simple Multi-Agent System that:

* Accepts a user request
* Breaks the request into subtasks
* Assigns work to specialized agents
* Combines results into a final response

Example Request:

```text
Create a report on AI in Healthcare
```

---

## Architecture

```text
User
  │
  ▼
Chat Trigger
  │
  ▼
Supervisor Agent
  │
  ▼
Research Agent
  │
  ▼
Writer Agent
  │
  ▼
Verifier Agent
  │
  ▼
Final Response
```

---

## Agents and Roles

### Supervisor Agent

Responsibilities:

* Understand user request
* Break task into subtasks
* Delegate work to worker agents

Example:

Input:

```text
Create a report on AI in Healthcare
```

Output:

```text
Research Task: Gather information about AI in Healthcare.

Writing Task: Create a structured report.

Verification Task: Review and improve the report.
```

---

### Research Agent

Responsibilities:

* Collect relevant information
* Identify benefits and challenges
* Gather examples and facts

Output Example:

```text
• AI assists in medical diagnosis
• AI improves patient monitoring
• AI supports drug discovery
• AI reduces administrative workload
```

---

### Writer Agent

Responsibilities:

* Convert research into a structured report
* Create introduction, body, and conclusion

Output Example:

```text
Title: AI in Healthcare

Introduction:
Artificial Intelligence is transforming healthcare by improving diagnosis, treatment planning, and operational efficiency.

Benefits:
• Faster diagnosis
• Improved patient outcomes
• Reduced costs

Challenges:
• Data privacy concerns
• Regulatory compliance

Conclusion:
AI has the potential to significantly improve healthcare services.
```

---

### Verifier Agent

Responsibilities:

* Review report quality
* Check grammar and clarity
* Improve final output

Output:

```text
Verified Final Report
```

---

## Agent Messaging Flow

### Step 1

User sends a request.

```text
Create a report on AI in Healthcare
```

### Step 2

Supervisor Agent analyzes the request.

### Step 3

Research Agent gathers information.

### Step 4

Writer Agent generates the report.

### Step 5

Verifier Agent reviews the report.

### Step 6

Final response is returned to the user.

---

## Tool Usage

The system can use external tools to improve results.

Examples:

* Web Search APIs
* Wikipedia API
* HTTP Request Node
* Google Sheets
* OpenAI Models

Research Agent may use tools to fetch real-world information before generating output.

---

## Single-Agent vs Multi-Agent

| Feature        | Single-Agent | Multi-Agent |
| -------------- | ------------ | ----------- |
| Agents         | 1            | Multiple    |
| Specialization | No           | Yes         |
| Scalability    | Limited      | High        |
| Collaboration  | No           | Yes         |
| Accuracy       | Moderate     | Higher      |

---

## n8n Workflow Components

1. Chat Trigger
2. Supervisor Agent
3. Research Agent
4. Writer Agent
5. Verifier Agent
6. Respond to Chat

---

## Example Execution

Input:

```text
Create a report on AI in Education
```

Workflow:

```text
User
 → Supervisor
 → Research Agent
 → Writer Agent
 → Verifier Agent
 → Final Report
```

Output:

```text
Title: AI in Education

Introduction
Artificial Intelligence is transforming education through personalized learning and automation.

Benefits
• Personalized learning
• Automated grading
• Intelligent tutoring

Challenges
• Data privacy
• Cost of implementation

Conclusion
AI can improve educational outcomes while introducing new challenges.
```

