# Support Workflow Example

## Goal

Use Flowvenue MCP to orchestrate customer support operations conversationally.

---

# Example Prompt

```txt
Create a support ticket for this customer and assign it to the technical team.
```

---

# Example Operational Flow

## 1. Read runtime context

Tools:
- `get_process_runtime_context`
- `list_instances`

---

## 2. Create or update operational records

Tools:
- `create_instance`
- `upsert_instance`

---

## 3. Trigger operational actions

Possible actions:
- notifications
- approval requests
- external connectors
- email workflows

---

# Runtime Benefits

Flowvenue maintains:
- conversational continuity
- operational context
- workflow state
- process orchestration

This allows AI agents to coordinate support operations conversationally.

---

# Important Security Principle

Flowvenue MCP does not expose destructive delete operations.

Support workflows operate through:
- create
- update
- orchestration
- runtime transitions

without unrestricted destructive capabilities.
