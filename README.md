# OpenCLI Adapter Dev 🚀

Turn any website, browser session, or Electron app into a standardized CLI. Built for AI Agents to discover, learn, and execute tools seamlessly.

[![NPM](https://img.shields.io/npm/v/@jackwener/opencli?style=flat-square)](https://www.npmjs.com/package/@jackwener/opencli)
[![License](https://img.shields.io/github/license/cheerhuan/opencli-skill-dev?style=flat-square)](https://github.com/cheerhuan/opencli-skill-dev/blob/main/LICENSE)

---

## 🌟 Features

- **AI-Native Runtime**: Designed specifically for AI Agents (Hermes, OpenClaw, Claude Code) to operate the web.
- **Zero-API Automation**: Control sites without official APIs by leveraging your logged-in browser session.
- **Deterministic Interface**: Transform flaky web interactions into reliable CLI commands.
- **Electron Control**: Extend CLI capabilities to desktop apps like Cursor, Notion, and ChatGPT.

## 🛠 Installation

### 1. Install OpenCLI Core
```bash
npm install -g @jackwener/opencli
```

### 2. Install this Skill
**For Hermes Agent / OpenClaw:**
```bash
# Use the official skill installer
hermes skill install https://github.com/cheerhuan/opencli-skill-dev
```

---

## 📖 How It Works

This skill implements a standardized **Recon $\rightarrow$ Design $\rightarrow$ Implement $\rightarrow$ Verify** workflow for creating CLI adapters:

1. **Recon**: `opencli browser analyze <url>` to detect WAF and page patterns.
2. **Design**: Map web elements to deterministic CLI arguments.
3. **Implement**: Write adapters using `wait xhr` for async stability.
4. **Verify**: `opencli browser verify` to ensure memory persistence and execution success.

## 🚀 Quick Start for AI Agents

Once installed, you can ask your agent:
> "Use the `opencli-adapter-dev` skill to help me create a CLI adapter for [Target Website]."

The agent will then autonomously handle the reconnaissance and implementation process.

---

## 📜 License
MIT License. See [LICENSE](LICENSE) for details.
