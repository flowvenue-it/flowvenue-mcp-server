# Conversational Process Design Example

## Goal

Use Claude Desktop and Flowvenue MCP to create operational workflows conversationally.

---

# Example Prompt

```txt
Create an employee onboarding workflow with approval steps.
```

---

# Example Runtime Flow

## 1. Read organization context

Tool:
- `get_org_build_context`

The MCP agent reads:
- existing processes
- objects
- fields
- roles
- connections

---

## 2. Bootstrap a draft process

Tool:
- `bootstrap_process_draft`

Example capabilities:
- create process draft
- create main object
- create initial fields
- create initial steps

---

## 3. Add operational actions

Tools:
- `add_action`
- `validate_action_config`
- `simulate_action_patch`

Example actions:
- approval requests
- emails
- runtime data collection
- external connectors

---

## 4. Validate the workflow

Tools:
- `validate_process_graph`
- `validate_process`

---

## 5. Runtime testing

Tools:
- `create_test_instance`
- `simulate_process_message`
- `evaluate_test_outcome`

---

## 6. Publish

Tools:
- `preview_process_publish_plan`
- `publish_process`

---

# Important

Flowvenue MCP enforces:
- structural validation
- runtime validation
- publish readiness checks
- operational guardrails

before workflows can be published.
