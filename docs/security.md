# Flowvenue MCP Security Model

## Overview

Flowvenue MCP was designed for enterprise operational safety.

The platform enforces:
- organizational isolation
- scoped operational permissions
- controlled runtime execution
- strict destructive-operation guardrails

---

# Core Principles

## Organization Isolation

Every MCP connection operates within a single Flowvenue organization context.

Authentication is bound to:
- an inbound System Connection
- the owning organization
- runtime capability configuration

Cross-organization access is not allowed.

---

## Capability-Based Access

Tool access is controlled through:
- `mcp_config.capabilities`
- `mcp_config.tools`
- runtime policies
- internal guardrails

A valid token alone does not grant unrestricted operational access.

---

# No Destructive Delete Policy

Flowvenue MCP does not expose destructive delete operations.

There are no public `delete_*` MCP tools.

The MCP layer does not allow deletion of:
- processes
- process instances
- runtime records
- schema objects
- schema fields
- process steps
- process actions
- persistent organizational data

Runtime write tools support:
- create
- update
- upsert

but not destructive removal.

Reserved delete-style operations are blocked by guardrails.

---

# Authentication Security

Production authentication uses:
- OAuth Bearer authentication
- opaque Flowvenue-issued MCP tokens
- inbound System Connection validation

Accepted MCP tokens use the prefix:

```txt
fv_mcp_
```

Tokens support:
- expiration
- revocation
- hashed storage
- organization binding

---

# Runtime Safety

Flowvenue MCP maintains:
- stateful validation
- runtime process consistency
- operational boundaries
- execution context awareness

This prevents unsafe cross-context operations.

---

# Auditability

Operational execution is designed to support:
- traceability
- runtime inspection
- execution visibility
- controlled enterprise operations

---

# Legacy Authentication

Legacy authentication modes may exist in non-production environments for compatibility purposes.

These modes are not the primary production authentication model.

Production environments are expected to use OAuth Bearer authentication.

---

# Security Philosophy

Flowvenue believes AI agents should execute operational workflows through constrained business capabilities rather than unrestricted low-level system access.
