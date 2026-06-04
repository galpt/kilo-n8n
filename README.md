# n8n Skills for Kilo Code

Expert n8n workflow skills for [Kilo Code](https://github.com/Kilo-Org/kilocode) — teaches AI agents how to build production-ready n8n workflows correctly.

## What This Is

This repository contains **7 knowledge skills** that give Kilo Code's AI models deep expertise in building n8n workflows. Each skill is a `SKILL.md` file with comprehensive reference material that the AI reads into context when the task matches the skill's description.

When you ask the AI to build or troubleshoot an n8n workflow, these skills ensure it:
- Uses the right workflow architectural pattern (webhook, API, database, AI agent, etc.)
- Writes correct expression syntax (avoiding common gotchas like `$json.body` vs `$json`)
- Writes correct JavaScript/Python in Code nodes
- Configures nodes with the right fields per operation
- Pre-empts common validation errors
- Knows what works and what doesn't in n8n

## Skills Included

| Skill | Description |
|---|---|
| **n8n-workflow-patterns** | 6 core architectural patterns, pattern selection guide, batch processing, integration gotchas (Google Sheets, Drive), data flow patterns |
| **n8n-expression-syntax** | Core variables (`$json`, `$node`, `$now`, `$env`), webhook data access, common mistakes catalog, when NOT to use expressions |
| **n8n-code-javascript** | `$input`/`$json`/`$node` API, SplitInBatches loop patterns, cross-iteration data, pairedItem, `$helpers` HTTP requests, DateTime |
| **n8n-code-python** | Python-specific API (`_input`/`_json`/`_node`), standard library usage, limitations vs JavaScript |
| **n8n-node-configuration** | Required fields per operation, `displayOptions` visibility rules, `patchNodeField` for surgical edits, property dependencies |
| **n8n-validation-expert** | Error types, validation profiles (minimal/runtime/ai-friendly/strict), false positives, auto-sanitization system, recovery strategies |
| **n8n-mcp-tools-expert** | Tool selection guide, nodeType format, validation profiles, smart parameters, auto-sanitization |

## How to Use

### Prerequisites

- [Kilo Code](https://github.com/Kilo-Org/kilocode) VS Code extension

### Installation

1. Open **Settings > Agent Behavior > Skills** in Kilo Code.
2. Under **Skill URLs**, add:
   ```
   https://raw.githubusercontent.com/galpt/kilo-n8n/main/skills/
   ```
3. Click **Add**, then start a **new session**.
4. Verify the skills are loaded by asking the AI:
   > "What n8n skills do you have available?"

The AI will list all 7 skills and use them automatically when your requests match their descriptions.

### How It Works Behind the Scenes

Kilo Code fetches the [`skills/index.json`](skills/index.json) manifest from this repo, downloads each skill's files to `~/.cache/kilo/skills/`, and injects the skill metadata into the AI's system prompt. When the AI determines a task matches a skill's description, it reads the full `SKILL.md` content into context.

## About the Skills

These skills were originally authored by [czlonkowski](https://github.com/czlonkowski) in the [n8n-skills](https://github.com/czlonkowski/n8n-skills) repository and are restructured here with an `index.json` manifest for Kilo Code compatibility. All skill content is licensed under the [MIT License](LICENSE).

The skills are designed as knowledge references — they teach the AI about n8n best practices, patterns, and pitfalls. They do not require an MCP server to provide value, though pairing them with the [n8n-mcp](https://github.com/czlonkowski/n8n-mcp) MCP server enables additional capabilities like node search and live workflow management.

## License

[MIT](LICENSE)
