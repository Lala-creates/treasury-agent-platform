# Treasury Agent Platform

A multi-agent AI platform that coordinates specialized treasury, liquidity, capital, risk, and business-analysis agents to complete complex financial-services workflows.

## Overview

Treasury Agent Platform demonstrates how an agentic system can decompose a business request, select appropriate tools, delegate work to domain-specialized agents, validate outputs, and return an auditable response.

The platform is designed around controlled orchestration rather than unrestricted autonomous behavior.

## Example Workflow

A user submits:

> Assess the impact of a new liquidity-policy requirement and prepare implementation recommendations.

The platform may invoke:

1. Regulatory Research Agent
2. Liquidity Subject-Matter Agent
3. Data Impact Agent
4. System Impact Agent
5. Business Analyst Agent
6. Risk and Controls Agent
7. Review Agent

The final output may include:

- Requirement summary
- Impacted processes
- Data requirements
- System impacts
- Risks and controls
- User stories
- Acceptance criteria
- Open questions

## Key Features

- Supervisor-agent orchestration
- Domain-specific agents
- Tool calling
- Shared state and memory
- Human approval checkpoints
- Structured outputs
- Agent-level logging
- Trace visualization
- Retry and fallback logic
- Evaluation of task completion
- Guardrails and permission boundaries

## Architecture

```text
User Request
     |
API Gateway
     |
Supervisor Agent
     |
Task Planner
     |
------------------------------------------------
| Regulatory | Liquidity | Capital | Data | BA |
------------------------------------------------
     |
Validation and Review Agent
     |
Human Approval
     |
Final Structured Deliverable
```

## Suggested Agent Roles

### Supervisor Agent

- Interprets the request
- Creates the task plan
- Assigns tasks
- Tracks completion
- Resolves conflicts

### Regulatory Agent

- Searches approved regulatory sources
- Extracts obligations
- Identifies effective dates and scope

### Treasury Agent

- Evaluates funding, liquidity, and balance-sheet implications

### Capital Agent

- Assesses capital, RWA, leverage, and reporting impacts

### Data Agent

- Identifies data elements, lineage, quality issues, and authoritative sources

### Business Analyst Agent

- Generates requirements, user stories, business rules, and acceptance criteria

### Risk and Controls Agent

- Identifies operational, model, compliance, and governance risks

### Reviewer Agent

- Checks consistency, citations, completeness, and unsupported claims

## Suggested Technology Stack

- Python
- FastAPI
- OpenAI API
- OpenAI Agents SDK or LangGraph
- Pydantic
- PostgreSQL
- Redis
- Celery or a queue-based worker
- Docker
- OpenTelemetry
- LangSmith
- Streamlit or React

## Repository Structure

```text
treasury-agent-platform/
├── app/
│   ├── agents/
│   ├── tools/
│   ├── workflows/
│   ├── guardrails/
│   ├── memory/
│   ├── evaluation/
│   └── api/
├── prompts/
├── schemas/
├── tests/
├── data/
├── .env.example
├── docker-compose.yml
└── README.md
```

## Example Structured Output

```json
{
  "request_id": "TR-2026-001",
  "summary": "The policy introduces...",
  "impacted_processes": [],
  "data_requirements": [],
  "system_impacts": [],
  "risks": [],
  "user_stories": [],
  "citations": [],
  "review_status": "approved_with_conditions"
}
```

## Getting Started

```bash
git clone https://github.com/<your-username>/treasury-agent-platform.git
cd treasury-agent-platform

python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

cp .env.example .env
uvicorn app.main:app --reload
```

## Guardrails

The platform should implement:

- Tool allowlists
- Read-only defaults
- Input and output validation
- Maximum iteration limits
- Cost and token limits
- Human approval for consequential actions
- Prompt-injection defenses
- Source restrictions
- Separation of planning and execution
- Complete trace logging

## Evaluation

Evaluate:

- Task-completion rate
- Tool-selection accuracy
- Citation quality
- Agent handoff quality
- Structured-output validity
- Error recovery
- Cost per completed task
- Latency
- Human-review acceptance rate

## Roadmap

- [ ] Supervisor workflow
- [ ] Domain-agent library
- [ ] Human approval interface
- [ ] Evaluation harness
- [ ] Trace dashboard
- [ ] Tool-permission system
- [ ] Cloud deployment
- [ ] Multi-tenant support

##  Value

This project demonstrates:

- Agentic AI architecture
- Workflow orchestration
- Tool calling
- Enterprise controls
- Financial-services expertise
- Structured-output design
- Production-minded system engineering

## Disclaimer

This project is for educational and portfolio purposes and should not be used for autonomous financial or regulatory decision-making.# treasury-agent-platform
