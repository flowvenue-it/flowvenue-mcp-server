# Flowvenue MCP Architecture

## Overview

Flowvenue MCP Server is the MCP integration layer of the Flowvenue platform.

It exposes conversational operational capabilities to AI agents through the Model Context Protocol (MCP).

The MCP server is not a standalone runtime. It is part of the Flowvenue backend and operates inside a licensed Flowvenue environment.

---

# High-Level Architecture

```txt
AI Client (Claude Desktop / Agent)
                ↓
        MCP Protocol Layer
                ↓
       Flowvenue MCP Server
                ↓
     Flowvenue Runtime Engine
                ↓
Processes • KPIs • Actions • State • APIs
```

---

# Runtime Model

Flowvenue is built around:
- conversational workflows
- stateful process execution
- operational orchestration
- runtime context navigation
- enterprise process management

The MCP layer exposes these capabilities as MCP tools.

---

# MCP Transport

Flowvenue MCP is exposed as HTTP endpoints served directly by the Flowvenue backend.

Example path:

```txt
/api/inbound/mcp/v1/
```

OAuth discovery is exposed through:

```txt
/.well-known/oauth-protected-resource
```

---

# Deployment Model

The MCP server is part of the Flowvenue application.

There is no separate standalone “MCP-only” runtime.

Deployment options:

- Flowvenue Cloud
- Private VPC deployments
- Self-hosted Flowvenue environments

In all cases, MCP runs as part of the Flowvenue platform.

---

# Operational Model

Flowvenue MCP exposes:
- runtime operations
- workflow orchestration
- process design
- schema management
- KPI exploration
- testing sandbox capabilities

The platform maintains:
- conversational state
- process state
- execution context
- organizational isolation

---

# Authorization Model

Authentication and authorization are separated.

## Authentication

Authentication validates:
- the MCP client
- the inbound connection
- the organization context

## Authorization

Authorization controls:
- which tools are visible
- which tools are callable
- which operational capabilities are enabled

Tool visibility depends on:
- `mcp_config.capabilities`
- `mcp_config.tools`
- delete policy restrictions
- legacy visibility settings

---

# Legacy Compatibility

Some MCP tools remain available for backward compatibility.

Legacy tools:
- may be hidden from `tools/list`
- remain callable through `tools/call`
- can be re-enabled in visibility configuration

This allows gradual migration without breaking existing integrations.

---

# Design Philosophy

Flowvenue MCP is designed around a core principle:

AI agents should operate enterprise workflows safely through controlled operational capabilities rather than unrestricted direct system access.
