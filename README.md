# Flowvenue MCP Server

> Turn AI agents into conversational business operators.

Flowvenue MCP Server allows AI assistants like Claude to create workflows, execute business processes, navigate operational contexts, query KPIs, and manage enterprise operations conversationally.

Built on the Model Context Protocol (MCP).

---

## What makes Flowvenue different?

Most MCP servers today expose:

- files
- static APIs
- retrieval tools
- generic functions

Flowvenue exposes:

- business processes
- conversational workflows
- operational runtime
- contextual execution
- enterprise orchestration

This is not just a tool server.

Flowvenue is a conversational operational runtime for AI agents.

---

## Core Capabilities

- Create business workflows conversationally
- Execute operational processes
- Navigate between business contexts
- Query KPIs and operational data
- Manage approvals and workflows
- Trigger enterprise actions
- Maintain stateful conversations
- Orchestrate multi-step business operations

---

## Example Use Cases

### CRM Operations

```txt
Show all open opportunities for ACME Corp.
```

```txt
Create a follow-up task for the sales team.
```

---

### HR Workflows

```txt
Create an employee onboarding workflow with approval steps.
```

```txt
Show all pending leave requests.
```

---

### Expense Management

```txt
Show all expense approvals for March over €500.
```

```txt
Approve the reimbursement for Marco Rossi.
```

---

### Customer Support

```txt
Create a support ticket for this customer and assign it to the technical team.
```

---

## Why This Matters

Traditional enterprise software was built around:

- menus
- forms
- dashboards
- fixed interfaces

AI agents are changing this model completely.

The future is conversational operations.

Flowvenue allows AI agents to operate real business processes through natural language.

---

## Architecture

```txt
Claude Desktop / AI Agent
            ↓
      MCP Protocol
            ↓
   Flowvenue MCP Server
            ↓
 Conversational Runtime
            ↓
Processes • KPIs • Actions • State • APIs
```

---

## Traditional MCP vs Flowvenue MCP

| Traditional MCP Servers | Flowvenue MCP |
|---|---|
| File retrieval | Business process execution |
| Stateless tools | Stateful workflows |
| Static APIs | Conversational runtime |
| Data access | Operational orchestration |
| Generic tooling | Enterprise process engine |
| Read-only interactions | Full operational execution |

---

## Quick Start

### 1. Install

```bash
npm install -g flowvenue-mcp-server
```

---

### 2. Configure Claude Desktop

Add this to your Claude Desktop MCP configuration:

```json
{
  "mcpServers": {
    "flowvenue": {
      "command": "npx",
      "args": ["flowvenue-mcp-server"],
      "env": {
        "FLOWVENUE_API_KEY": "your_api_key",
        "FLOWVENUE_BASE_URL": "https://your-flowvenue-instance.com"
      }
    }
  }
}
```

---

### 3. Start Using Flowvenue

Example prompts:

```txt
Create a customer onboarding workflow.
```

```txt
Show all pending approvals.
```

```txt
Generate KPI insights for sales performance.
```

```txt
Create a support ticket for this client and schedule a follow-up meeting.
```

---

## Security Philosophy

Flowvenue was designed with enterprise operational safety in mind.

### Security Principles

- Organization isolation
- Scoped permissions
- Audit trail support
- Context-aware execution
- Rate limiting
- Stateful process validation
- Controlled operational boundaries

### Important Principle

AI agents should not have unrestricted destructive capabilities.

For this reason, Flowvenue enforces strict operational guardrails around sensitive actions and enterprise data.

---

## Supported AI Clients

- Claude Desktop
- MCP-compatible AI assistants
- Agentic frameworks
- IDE integrations
- Conversational enterprise agents

---

## Example Enterprise Scenarios

### Conversational CRM

```txt
Show all customers from Rome and create a meeting with the most recent one.
```

---

### Cross-Process Navigation

```txt
Create an invoice for this customer and open a support ticket for the pending issue.
```

---

### KPI Exploration

```txt
Show sales trends for the last quarter grouped by region.
```

---

## Vision

Software interfaces are becoming obsolete.

The future is:

- conversational operations
- programmable enterprises
- AI-native workflows
- operational intelligence

Flowvenue enables organizations to become conversationally programmable.

---

## Roadmap

- Advanced agent orchestration
- Multi-agent collaboration
- Enterprise memory layers
- Conversational analytics
- AI-driven workflow optimization
- Cross-system operational execution

---

## Documentation

Additional documentation coming soon:

- Authentication
- Tool reference
- Workflow orchestration
- Security model
- Enterprise deployment
- KPI runtime
- Conversational state management

---

## Contributing

Contributions, feedback, and ideas are welcome.

We believe the future of enterprise software is conversational.

---

## License

MIT License

---

## Links

- Website: https://flowvenue.com
- MCP Protocol: https://modelcontextprotocol.io
- Claude Desktop: https://claude.ai/download

---

## Final Thought

The browser was only the beginning.

The real transformation is that software itself is becoming conversational.
