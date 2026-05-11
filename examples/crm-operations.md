# CRM Operations Example

## Goal

Use Claude Desktop connected to Flowvenue MCP to navigate CRM operations conversationally.

---

# Example Prompts

## List active opportunities

```txt
Show all open opportunities for ACME Corp.
```

---

## Create a follow-up operation

```txt
Create a follow-up task for the sales team.
```

---

## Navigate across operational contexts

```txt
Show all customers from Rome and create a meeting with the most recent one.
```

---

# MCP Capabilities Used

- `list_instances`
- `get_process_runtime_context`
- `upsert_instance`
- `send_message`

---

# Runtime Characteristics

Flowvenue maintains:
- conversational state
- process context
- operational continuity

This allows AI agents to operate CRM workflows conversationally instead of through static interfaces.
