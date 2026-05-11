# Flowvenue MCP Tools

## Overview

Flowvenue MCP exposes operational enterprise capabilities through MCP tools.

Tools are grouped into:
- runtime operations
- process design
- schema management
- testing sandbox
- publishing workflows

Tool visibility depends on runtime authorization policies.

---

# Meta Tools

- `connection_context`
- `list_capabilities`

---

# Runtime Chat

- `send_chat_message`
- `send_message`

---

# Runtime Read

- `list_instances`
- `get_process_runtime_context`

---

# Runtime Write

- `upsert_record`
- `upsert_instance`
- `create_instance`

---

# Process Design Read

- `get_process_schema`
- `get_process_structure`
- `list_processes`
- `list_process_steps`
- `validate_process_publish_readiness`
- `validate_process`
- `get_process_action_summary`
- `get_step_detail`
- `get_build_pipeline`
- `get_org_build_context`
- `get_roles`
- `get_supported_action_types`
- `get_action_schema`
- `validate_action_config`
- `get_process_graph_snapshot`
- `validate_process_graph`
- `simulate_action_patch`
- `suggest_next_build_steps`

---

# Process Design Create

- `create_process_draft`
- `create_process`
- `bootstrap_process_draft`

---

# Process Design Patch

- `create_step`
- `update_step`
- `patch_process_draft`
- `update_process`
- `create_process_step_draft`
- `create_process_action_draft`
- `add_action`
- `patch_process_action_draft`
- `update_action`
- `reorder_process_actions_draft`
- `create_role`
- `repair_process_from_test`

---

# Publish

- `preview_process_publish_plan`
- `publish_process`

---

# Object Schema

- `get_action_object_fields_compact`
- `get_objects`
- `get_supported_field_types`
- `create_object`
- `add_field`

---

# Test Sandbox

- `create_test_instance`
- `simulate_process_message`
- `get_test_execution_log`
- `evaluate_test_outcome`

---

# Legacy Tool Visibility

Some tools are considered legacy compatibility tools.

By default:
- they may be hidden from `tools/list`
- they remain callable through `tools/call`

Legacy visibility can be enabled through runtime configuration.

---

# Tool Authorization

Tool availability depends on:
- `mcp_config.capabilities`
- `mcp_config.tools`
- delete policy restrictions
- runtime guardrails

Tool access is resolved dynamically at runtime.
