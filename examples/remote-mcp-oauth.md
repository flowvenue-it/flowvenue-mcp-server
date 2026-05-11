# Remote MCP OAuth Setup

## Overview

Flowvenue MCP is exposed as a remote MCP server over HTTPS.

It is not a local stdio MCP server and does not require running a standalone MCP process through `npx` or local runtime wrappers.

The MCP runtime is part of the Flowvenue backend.

---

# MCP Endpoint

Production example:

```txt
https://your-flowvenue-instance.com/api/inbound/mcp/v1
```

Local development example:

```txt
http://localhost:3000/api/inbound/mcp/v1
```

---

# OAuth Endpoints

Authorization URL:

```txt
https://your-flowvenue-instance.com/oauth/mcp/authorize
```

Token URL:

```txt
https://your-flowvenue-instance.com/oauth/mcp/token
```

---

# Authentication Model

Flowvenue MCP uses OAuth Bearer authentication.

After OAuth authorization, the MCP client receives an opaque Flowvenue MCP token.

Accepted MCP tokens use the prefix:

```txt
fv_mcp_
```

All MCP requests must send:

```http
Authorization: Bearer <fv_mcp_token>
```

---

# Organization Context

Every MCP token is bound to:

- a Flowvenue organization
- an inbound System Connection
- runtime capability configuration

After authentication, Flowvenue resolves:
- organization context
- MCP capabilities
- allowed tools
- runtime permissions

---

# Transport Model

Flowvenue MCP supports multiple HTTP interaction models.

## JSON-RPC over HTTP

```http
POST /api/inbound/mcp/v1
Content-Type: application/json
```

---

## Streamable HTTP / SSE Handshake

```http
GET /api/inbound/mcp/v1
Accept: text/event-stream
```

---

## SSE JSON-RPC Responses

```http
POST /api/inbound/mcp/v1
Accept: text/event-stream
```

---

# Important Notes

## Flowvenue MCP is not a stdio server

This repository does not expose:
- local stdio MCP runtime
- standalone npm MCP process
- `npx` MCP launcher
- embedded MCP CLI server

The MCP runtime is served directly by the Flowvenue backend over HTTPS.

---

## Licensing Requirement

Using Flowvenue MCP requires:

- a licensed Flowvenue organization
- an active inbound System Connection
- MCP enabled on the connection
- valid OAuth authentication

---

# Legacy Authentication

Legacy inbound authentication modes may exist in non-production environments for compatibility purposes.

Examples:
- Basic authentication
- `X-Consumer-Key`
- `X-Consumer-Secret`

These mechanisms are not the recommended production authentication model.

Production environments are expected to use OAuth Bearer authentication.

---

# Security Philosophy

Flowvenue MCP was designed around controlled operational execution.

The platform intentionally avoids unrestricted destructive runtime capabilities.

There are no public destructive delete tools exposed through MCP.
