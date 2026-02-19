# OpenClaw Agent Builder

A visual, browser-based configuration editor for [OpenClaw](https://github.com/openclaw/openclaw) agent configs.

## Features

- **Visual Agent Editor** — Add, edit, and delete agents with a friendly UI
- **Tool Profile Management** — Select from preset tool profiles (Minimal, Coding, Messaging, Full) or customize per-agent
- **Import Existing Configs** — Load your existing `openclaw.json` and edit visually
- **Full Config Preservation** — Imports keep all non-agent sections (channels, gateway, plugins, etc.)
- **Schema Validation** — Validates config structure and warns about issues
- **Diff View** — See exactly what changes you've made from the original config
- **OpenClaw Schema Compliant** — Outputs proper OpenClaw v2026.x config format

## Usage

1. Open `index.html` in a web browser
2. Either:
   - Click **Choose File** to load an existing `openclaw.json`
   - Or paste config JSON and click **Import Pasted Config**
3. Edit agents, tools, skills, channels, etc.
4. Click **📋 Copy** to copy the generated config
5. Paste into your `~/.openclaw/openclaw.json`

## Import Options

- **File Upload** — Select a `.json` config file
- **Paste** — Paste JSON directly into the textarea

## Generated Output

The tool generates a complete `openclaw.json` including:
- `agents.defaults` — Global defaults (model, timeout, etc.)
- `agents.list` — All agent configurations
- All other sections from imported config (channels, gateway, plugins, etc.)

## Schema Compatibility

Output conforms to OpenClaw v2026.x schema:
- Model: `{ primary: "...", fallbacks: [...] }`
- Timeout: `timeoutSeconds` (not `sessionTimeout`)
- Thinking: `thinkingDefault` (not `thinking`)

## Development

This is a single-file HTML application using Tailwind CSS (via CDN for development).

## License

MIT
