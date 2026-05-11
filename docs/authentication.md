# Flowvenue MCP Authentication

## Overview

Flowvenue MCP uses OAuth-based Bearer authentication.

The MCP authentication layer is tied to:
- Flowvenue organizations
- inbound System Connections
- runtime capability configuration

---

# Production Authentication

Production environments use opaque Flowvenue-issued MCP tokens.

Clients authenticate using:

```http
Authorization: Bearer <token>
```

Accepted MCP tokens use the prefix:

```txt
fv_mcp_
```

Tokens are:
- opaque
- organization-scoped
- revocable
- expiration-aware
- validated against Flowvenue storage

---

# System Connection Binding

Every MCP token is associated with:
- an inbound System Connection
- a specific organization
- runtime MCP configuration

After authentication:
- the organization context is loaded
- MCP capabilities are resolved
- tool authorization is applied

---

# OAuth Resource Discovery

Flowvenue exposes OAuth resource discovery metadata through:

```txt
/.well-known/oauth-protected-resource
```

This allows MCP-compatible clients to identify protected resources and authentication requirements.

---

# Authentication vs Authorization

Flowvenue separates:
- authentication
- authorization

## Authentication

Authentication validates:
- the token
- the connection
- the organization context

## Authorization

Authorization controls:
- visible tools
- callable tools
- operational capabilities

Authorization depends on:
- `mcp_config.capabilities`
- `mcp_config.tools`
- runtime policies
- security guardrails

---

# Legacy Authentication

Non-production environments may optionally support legacy inbound authentication mechanisms such as:
- Basic authentication
- `X-Consumer-Key`
- `X-Consumer-Secret`

These compatibility paths are not the recommended production model.

---

# Deployment Model

Flowvenue MCP authentication is part of the Flowvenue platform runtime.

There is no standalone authentication server separate from Flowvenue.
