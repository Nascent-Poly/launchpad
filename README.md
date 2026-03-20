# Launchpad — Natural Language Commands for VS Code

Stop memorizing command names. Just describe what you want and Launchpad runs it.

Press **Ctrl+Shift+.** and type plain English like "run my tests", "commit changes", or "zoom in" — Launchpad instantly understands and executes the right VS Code command.

Or press **Ctrl+Shift+/** and **say it out loud** — Launchpad listens, transcribes, and runs your command. No cloud, no API keys.

[![VS Code Marketplace](https://img.shields.io/visual-studio-marketplace/v/NascentPoly.launchpad-command-palette?label=VS%20Code%20Marketplace&color=blue)](https://marketplace.visualstudio.com/items?itemName=NascentPoly.launchpad-command-palette)
[![Installs](https://img.shields.io/visual-studio-marketplace/i/NascentPoly.launchpad-command-palette?color=green)](https://marketplace.visualstudio.com/items?itemName=NascentPoly.launchpad-command-palette)

## Why Launchpad?

- **195 commands** — covers files, git, testing, debugging, editing, terminals, themes, and more
- **Sub-3ms** — classification is instantaneous, no loading spinners
- **100% offline** — no API keys, no cloud calls, no telemetry. Everything runs locally in your editor
- **Zero dependencies** — nothing to install or configure beyond the extension itself

### Upgrade to Pro

Unlock the full power of Launchpad:

- **Voice commands** — speak instead of type with `Ctrl+Shift+/`
- **Visual Configurator** — Simple & Pro modes for building custom shortcuts and workflows
- **Preset Packs** — Space Command Center, DevOps Mission Control, Git Flight Deck, and more
- **Action Runner** — chain opens, goto, type, select, snippets, and delays into one-word macros
- **Script Generator** — say "create a flask server" and get a complete, ready-to-run file
- **Usage Statistics** — track your most-used commands and productivity patterns

Run **Launchpad: Activate Pro License** from the Command Palette, or visit [nascentpoly.com/pro](https://www.nascentpoly.com/pro).

## Quick Start

1. Install from the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=NascentPoly.launchpad-command-palette)
2. Press `Ctrl+Shift+.` (or `Cmd+Shift+.` on Mac) to type a command
3. Press `Ctrl+Shift+/` (or `Cmd+Shift+/` on Mac) to speak a command
4. Done.

## Examples

| You type | Launchpad runs |
|---|---|
| "run my tests" | Test: Run All Tests |
| "commit changes" | Git: Commit |
| "format the code" | Format Document |
| "open the terminal" | Toggle Terminal |
| "go to definition" | Go to Definition |
| "change theme" | Color Theme picker |
| "close all tabs" | Close All Editors |
| "toggle comment" | Toggle Line Comment |
| "deploy to production" | Run Build Task |
| "zoom in" | Zoom In |

## Voice Commands (Pro)

Press `Ctrl+Shift+/` and speak naturally. Launchpad uses the browser's built-in speech recognition (no cloud services) to transcribe your voice and classify the command.

- **Fully offline** — speech is processed locally in VS Code's webview
- **Same intent engine** — your voice goes through the same 195-intent classifier
- **Compound commands** — say "format and save" and both execute in sequence
- **Configurable** — set `launchpad.voiceLanguage` (default: `en-US`) and `launchpad.voiceTimeout` (default: 8s)

Use **Launchpad: Voice Command (with trace)** from the Command Palette to see ranked results from your spoken input.

## Visual Configurator (Pro)

Run **Launchpad: Configure** from the Command Palette to open the visual configurator.

- **Simple mode** (default) — designed for non-technical users. Friendly labels, dropdown menus with categorized VS Code actions, visual workflow blocks with icons. No command IDs to memorize.
- **Pro mode** — full control. Raw command ID inputs, all 7 action types exposed, Built-in Intents browser with all 195 intents.

Toggle between modes with the **Simple / Pro** switch in the top-right corner.

### Preset Packs

Load a preset to instantly populate your shortcuts and workflows:

| Preset | What you get |
|---|---|
| **Space Command Center** | 18 commands + 4 macros — "launch sequence", "abort mission", "pre-flight check" |
| **DevOps Mission Control** | 10 commands + 3 macros — "pipeline status", "rollback deploy" |
| **Power User Essentials** | 12 commands + 3 macros — "deep focus", "save and format" |
| **Git Flight Deck** | 12 commands + 3 macros — "clean commit", "sync up", "quick push" |
| **Script Generator** | 16 commands + 1 macro — "create a flask server", "write a dockerfile" |
| **Workspace Launcher** | 4 commands + 9 macros — "my app", "morning standup", "new branch" |

Presets merge with your existing config — they never overwrite.

## Action Runner (Pro)

Macros support 7 action types beyond simple VS Code commands:

| Action | What it does | Example |
|---|---|---|
| `command` | Run a VS Code command | `{ "action": "command", "command": "git.pull" }` |
| `open` | Open a file or folder | `{ "action": "open", "path": "C:/projects/my-app" }` |
| `goto` | Jump to line and column | `{ "action": "goto", "line": 42, "col": 1 }` |
| `type` | Insert text at cursor | `{ "action": "type", "text": "npm run dev\n" }` |
| `select` | Select a text range | `{ "action": "select", "from": {"line":1,"col":1}, "to": {"line":1,"col":20} }` |
| `snippet` | Insert a VS Code snippet | `{ "action": "snippet", "body": "console.log($1);$0" }` |
| `delay` | Wait before next step | `{ "action": "delay", "ms": 500 }` |

Plain string steps still work for backward compatibility.

### Example: One-word workspace launcher

```json
"launchpad.macros": {
    "my app": [
        { "action": "open", "path": "C:/projects/my-app" },
        { "action": "command", "command": "workbench.action.terminal.new" },
        { "action": "delay", "ms": 300 },
        { "action": "type", "text": "npm run dev\n" }
    ]
}
```

Say **"my app"** and your project opens, a terminal spawns, and your dev server starts.

## Script Generator (Pro)

Say **"create a flask server"** or **"write a dockerfile"** and Launchpad generates a complete, working file. 14 templates included:

Flask, Express, FastAPI, React Component, HTML5 Landing Page, Dockerfile, GitHub Actions CI, Bash Deploy Script, Python CLI, WebSocket Server, Data Pipeline, Jest Tests, Pytest Tests, Makefile

Run **Launchpad: Browse Templates** to pick from the full catalog.

## Trace Mode

Want to see how Launchpad ranked the candidates? Run **Launchpad: Run Command (with trace)** from the Command Palette to get a ranked list with confidence scores.

## Usage Stats (Pro)

Run **Launchpad: Show Usage Stats** to see a breakdown of your most-used commands, classification sources, and confidence scores. All data stored locally — never transmitted.

## License Management

- **Launchpad: Activate Pro License** — enter your license key to unlock Pro features
- **Launchpad: Manage License** — view status, deactivate, or upgrade
- Purchase a Pro license at [nascentpoly.com/pro](https://www.nascentpoly.com/pro)

## Supported Categories

| Category | Example commands |
|---|---|
| **File Operations** | create, delete, rename, open, save, close files |
| **Version Control** | commit, push, pull, branch, merge, stash, diff, rollback |
| **Code Quality** | format, lint, refactor |
| **Testing & Debugging** | run tests, debug, breakpoints, fix errors |
| **Build & Deploy** | build, deploy, install dependencies |
| **Search & Generate** | search code, generate snippets |
| **Editor Actions** | split editor, toggle sidebar/terminal, go to line, find & replace |
| **Editing** | comment, duplicate/delete lines, select occurrences, undo/redo |
| **Settings** | themes, minimap, word wrap, zoom |

## Requirements

- VS Code 1.90 or later
- That's it. No runtime dependencies.

## License

Proprietary — see [LICENSE](LICENSE) for details.

---

Made by **[Nascent Poly](https://www.nascentpoly.com)**
