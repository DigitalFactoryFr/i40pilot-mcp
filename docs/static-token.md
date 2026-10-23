# Static project token

For a script, a CI job or a service integration where nobody can sign in interactively.

1. In i40Pilot, open your project → **Connections** → **MCP tokens**.
2. Create a token. Choose read-only or read-write, and optionally restrict domains or tools.
3. Send it as a bearer header:

```bash
curl -s https://api.i40pilot.app/mcp \
  -H "Authorization: Bearer $I40PILOT_MCP_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

A static token identifies the **project**, not a person. Prefer OAuth whenever a human is in the loop.
Tokens are stored hashed: copy it when it is shown, it cannot be displayed again.
