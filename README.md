# @lobsterkit/db-mcp

MCP server for [LobsterDB](https://theclawdepot.com/db) — managed PostgreSQL for AI agents. Provision databases, run SQL, evolve schemas with tracked migrations. No API keys, no human signup, no configuration.

## Quick Start

Add to your MCP config (`.mcp.json`, `claude_desktop_config.json`, `.cursor/mcp.json`, etc.):

```json
{
  "mcpServers": {
    "lobsterdb": {
      "command": "npx",
      "args": ["-y", "@lobsterkit/db-mcp@0.1.0"]
    }
  }
}
```

On first use, an account is created automatically and your token is saved to `~/.lobsterdb/token`.

## Tools

| Tool | Description |
|------|-------------|
| `create_database` | Provision a new Postgres database |
| `list_databases` | List all databases on the account |
| `get_database` | Get details and connection string for a database |
| `delete_database` | Permanently delete a database |
| `query` | Run parameterized SQL — SELECT, INSERT, UPDATE, DELETE. Supports multi-statement SQL. |
| `introspect_schema` | Get table/column schema optimized for LLM context |
| `migrate` | Apply tracked, idempotent DDL migrations |
| `list_migrations` | Show schema change history |
| `snapshot` | Create a point-in-time backup (Builder+) |
| `get_account` | View tier, limits, and usage |

## Environment Variables

| Variable | Description |
|----------|-------------|
| `LOBSTERDB_API_KEY` | API key (skips auto-signup and file persistence) |
| `LOBSTERDB_API_URL` | Custom API base URL (default: `https://api.theclawdepot.com/db`) |

## Links

- **Website**: [theclawdepot.com/db](https://theclawdepot.com/db)
- **SDK**: [@lobsterkit/db](https://www.npmjs.com/package/@lobsterkit/db)
- **API docs**: [api.theclawdepot.com/db/docs](https://api.theclawdepot.com/db/docs)

## LobsterKit Ecosystem

This MCP server is part of the LobsterKit multi-product ecosystem. Accounts can be linked across LobsterVault, LobsterDB, and LobsterMail using a `linkToken` at signup, enabling a single Stripe customer and an automatic 15% multi-product discount.

## License

MIT
