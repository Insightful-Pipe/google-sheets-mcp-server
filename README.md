# Google Sheets MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/google-sheets)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect Google Sheets to AI assistants: read, write and format spreadsheet data.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use Google Sheets from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/google-sheets-icon.svg" alt="Google Sheets MCP Server" width="64" height="64">

## MCP Server URL

```
https://google-sheets.insightfulmcp.com/
```

## What is Google Sheets MCP?

Google Sheets MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. Preview tabs, headers, and targeted ranges from connected Google Sheets to pair manual data with AI workflows.

## Installation

### Claude

1. Copy the MCP Server URL: `https://google-sheets.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://google-sheets.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http google-sheets https://google-sheets.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "google-sheets": {
      "url": "https://google-sheets.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

26 actions: 3 read, 23 write.

### Read Actions (3)

| Action | Description |
|--------|-------------|
| `get_sheet_peak` | Peek at sheet to see available columns and sample data |
| `list_sheets` | List sheet/tab metadata inside a spreadsheet (sheet_id, title, index, optional gridProperties) |
| `query_sheet_data` | Query sheet data with SQL-like operations (SELECT, WHERE) |

### Write Actions (23)

| Action | Description |
|--------|-------------|
| `add_banding` | Apply alternating (banded) row colours to a range |
| `add_conditional_format` | Add a conditional formatting rule (colour scale or boolean condition) to a range |
| `add_filter_view` | Create a named saved filter view that can be activated later |
| `add_named_range` | Create a named range that can be referenced in formulas across the spreadsheet |
| `add_protected_range` | Lock a cell range so that only editors you choose can modify it |
| `add_rows` | Insert blank rows into a sheet (default inserts at the end) |
| `add_slicer` | Add an interactive slicer (filter control) anchored to a sheet |
| `auto_resize` | Auto-fit column widths or row heights to content |
| `batch_update_cells` | Update multiple ranges in a single call by providing a mapping of range => 2D array of values |
| `create_chart` | Add an embedded chart (bar, line, pie, column, area, scatter) to a sheet |
| `create_sheet` | Add a new tab to an existing spreadsheet with optional row/column counts and index |
| `delete_chart` | Remove an embedded chart from the spreadsheet |
| `duplicate_sheet` | Clone an existing sheet tab into a new tab within the same spreadsheet |
| `format_cells` | Apply formatting (bold, colours, fonts, number formats, alignment) to a cell range |
| `merge_cells` | Merge a range of cells into one |
| `set_basic_filter` | Set the basic auto-filter on a sheet range (shows filter dropdowns in column headers) |
| `set_data_validation` | Add a data validation rule (drop-down list, number constraint, etc.) to a range |
| `sort_range` | Sort a range of cells by one or more columns |
| `unmerge_cells` | Unmerge previously merged cells in a range |
| `update_borders` | Set or clear borders on a cell range |
| `update_cells` | Overwrite a contiguous range of cells with the provided 2D array of values |
| `update_sheet_properties` | Rename a tab, change its tab colour, freeze rows/columns, or hide/show it |
| `update_slicer` | Modify an existing slicer's column index or data range |

## Control What Your AI Can Do

You decide what AI agents can do with each connected account:

- **Turn individual actions on or off** for every connected account, so agents only see the actions you allow.
- **Connect as Read-only or Read & Write.** A read-only connection can only enable read actions.
- **Destructive actions stay off by default.** Actions such as deletes are disabled until an admin enables them.
- **Team access per account.** Restricted team members only use the accounts they are granted, with the read actions enabled on them.

## Usage Examples

```
"Summarize the tabs and headers in my "Q3 Budget" spreadsheet"
```

```
"Add a row to the Leads sheet with today's form submissions"
```

```
"Create a chart of monthly revenue"
```

## Ready-Made Skills and Prompts

- [Spreadsheet Data Overview](https://insightfulpipe.com/marketing-prompts-library/google-sheets-spreadsheet-data-overview)
- [Custom Report Builder From Sheets](https://insightfulpipe.com/marketing-prompts-library/google-sheets-custom-report-builder-from-sheets)
- [Campaign Tracking Sheet Analysis](https://insightfulpipe.com/marketing-prompts-library/google-sheets-campaign-tracking-sheet-analysis)

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [BigQuery MCP](https://insightfulpipe.com/mcp-servers/bigquery)
- [Airtable MCP](https://insightfulpipe.com/mcp-servers/airtable)
- [Notion MCP](https://insightfulpipe.com/mcp-servers/notion)
- [PostgreSQL MCP](https://insightfulpipe.com/mcp-servers/postgresql)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs/connectors-google-sheets)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
