# i40Pilot MCP server

**Build manufacturing dashboards, OEE reports, schedules and 3D parts from Claude, ChatGPT, Cursor or any MCP client.**

[i40Pilot](https://i40pilot.app?utm_source=github&utm_medium=mcp_readme) is an industrial BI platform. This repository documents its hosted
[Model Context Protocol](https://modelcontextprotocol.io) server. Point your client at one URL, sign in, and your AI assistant can
read and build in your i40Pilot project.

```
https://api.i40pilot.app/mcp
```

No install, no API key to copy: the server uses **OAuth 2.1** (PKCE, dynamic client registration). You choose the
project and **read-only or read-write** access on the consent screen, and you can revoke it at any time.

> 🇫🇷 *Serveur MCP hébergé d'i40Pilot : collez l'URL ci-dessus dans votre client IA, connectez-vous, choisissez le projet
> et le niveau d'accès. Votre assistant peut alors lire et construire tableaux de bord, TRS/OEE, plannings et pièces 3D.*

<!-- TODO before going public: add demo GIF here (prompt → dashboard in 30 s) -->

## What you can ask

- *"Connect my production database and build an OEE dashboard per line, with availability, performance and quality."*
- *"Read the downtime sheet I uploaded and add a Pareto of stop causes."*
- *"Plan the maintenance shutdown: these 12 tasks, these dependencies — give me the critical path."*
- *"Model a 40 mm aluminium mounting bracket with two M6 holes and show me a render."*
- *"Export this dashboard to Power BI."*

## Connect your client

| Client | How |
|---|---|
| **Claude.ai / Claude Desktop** | Settings → Connectors → *Add custom connector* → paste the URL → *Connect* |
| **ChatGPT** | Settings → Connectors → *Create* → paste the URL → OAuth |
| **Claude Code** | `claude mcp add --transport http i40pilot https://api.i40pilot.app/mcp` then `/mcp` to sign in |
| **Cursor** | add [`examples/cursor-mcp.json`](examples/cursor-mcp.json) to `.cursor/mcp.json` |
| **VS Code** | add [`examples/vscode-mcp.json`](examples/vscode-mcp.json) to `.vscode/mcp.json` |
| **Scripts / services** | a static project token, see [docs/static-token.md](docs/static-token.md) |

You need an i40Pilot account — [create one free](https://i40pilot.app?utm_source=github&utm_medium=mcp_readme).

## Tools

56 tools across 9 areas, plus a conversational entry point. Full list: [docs/tools.md](docs/tools.md).

| Area | Examples |
|---|---|
| **Agent** | `i40pilot_chat` — hand a whole request to the i40Pilot agent, in plain language |
| **Dashboards (BI)** | `bi_create_dashboard`, `bi_add_widget`, `bi_run_dashboard_agent`, `bi_export_powerbi` |
| **Data sources** | `bi_create_data_source_from_template`, `bi_introspect_schema`, `bi_create_dataset`, `bi_add_computed_column` |
| **Spreadsheets** | `spreadsheet_create_workbook_from_file`, `spreadsheet_read_context`, `spreadsheet_update_rows` |
| **Scheduling** | `schedule_cpm`, `schedule_dates`, `gantt_append_task`, `gantt_update_data` |
| **3D CAD (text-to-CAD)** | `drawboard_run_program`, `drawboard_view_render`, `drawboard_inspect_part` |
| **Calendar, forms, drive, infographics** | `calendar_create_events`, `forms_append_field`, `drive_create_upload_url`, `infographic_generate` |

The tool list is served live by the server (`tools/list`): new capabilities appear without any update on your side.

## Security

- **Read-only by default.** Write tools only appear when you grant write access.
- **Scoped to one project.** A token can never reach another project.
- **Runs as you.** OAuth calls execute under your own row-level permissions.
- **Revocable.** Remove the connection from your client or from *Connections* in i40Pilot.

Found a vulnerability? Use **Security → Report a vulnerability** on this repository (private) — please do not open a public issue.

## Feedback

Bug, missing tool, client that doesn't connect? [Open an issue](../../issues). Tell us which client and what you asked.

## License

The documentation and examples in this repository are MIT-licensed. The i40Pilot service itself is proprietary.
