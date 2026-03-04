# OpenClaw Agent Builder

Single-file HTML app (`index.html`) — no build step, no dependencies beyond Tailwind CDN.

## Project Structure

- `index.html` — entire app: HTML, CSS (Tailwind + inline), and JavaScript

## How It Works

All logic lives in one `<script>` block at the bottom of `index.html`:

- **`agents[]`** — in-memory array of agent state objects
- **`channelConfigs[]`** — in-memory array of top-level channel configs
- **`originalFullConfig`** — stores the full imported JSON for round-trip preservation
- **`buildConfig()`** — serializes all state to `openclaw.json` format
- **`parseAndLoadConfig(config)`** — deserializes imported JSON into UI state
- **`render()`** — rebuilds all agent card HTML and updates the config output

## Key Schema Notes (OpenClaw v2026.x)

- Agent-level timeout: `timeoutSeconds` (not `sessionTimeout`)
- Global thinking: `thinkingDefault` (not `thinking`)
- Model field: `{ primary: "...", fallbacks: [...] }`
- Tools: `{ profile, alsoAllow, deny }` or `{ allow }`
- Agent messaging: `sessionTargets.allow[]`
- Subagents: `subagents.allowAgents[]`

## Development

Open `index.html` directly in a browser — no server needed.
