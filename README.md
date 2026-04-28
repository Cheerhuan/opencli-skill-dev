<div align="center">

# OpenCLI Adapter Dev 🚀

![OpenCLI Hero](assets/hero.jpg)

**Turn any website, browser session, or Electron app into a standardized CLI. Built for AI Agents to discover, learn, and execute tools seamlessly.**
**將任何網站、瀏覽器會話或 Electron App 轉化為標準化 CLI。專為 AI Agent 設計，使其能無縫發現、學習並執行工具。**

[![NPM](https://img.shields.io/npm/v/@jackwener/opencli?style=flat-square)](https://www.npmjs.com/package/@jackwener/opencli)
[![License](https://img.shields.io/github/license/cheerhuan/opencli-skill-dev?style=flat-square)](https://github.com/cheerhuan/opencli-skill-dev/blob/main/LICENSE)

</div>

---

## 📌 Table of Contents | 目錄
- [🌟 Features | 功能特色](#-features--功能特色)
- [🛠 Installation | 安裝指南](#-installation--安裝指南)
- [📖 How It Works | 工作原理](#-how-it-works--工作原理)
- [🚀 Quick Start | 快速上手](#-quick-start-for-ai-agents--ai-agent-快速上手)
- [📜 License | 授權協議](#-license--授權協議)

---

## 🌟 Features | 功能特色

| Feature | 說明 | Description |
| :--- | :--- | :--- |
| **AI-Native Runtime** | **AI 原生運行時** | Designed specifically for AI Agents (Hermes, OpenClaw, Claude Code) to operate the web. <br> 專為 AI Agent 設計，使其能高效操作網頁。 |
| **Zero-API Automation** | **零 API 自動化** | Control sites without official APIs by leveraging your logged-in browser session. <br> 利用已登入的瀏覽器會話，在無需官方 API 的情況下控制網站。 |
| **Deterministic Interface** | **確定性接口** | Transform flaky web interactions into reliable CLI commands. <br> 將不穩定的網頁交互轉化為可靠的 CLI 命令。 |
| **Electron Control** | **Electron 應用控制** | Extend CLI capabilities to desktop apps like Cursor, Notion, and ChatGPT. <br> 將 CLI 能力擴展至 Cursor, Notion, ChatGPT 等 Electron 桌面應用。 |

---

## 🛠 Installation | 安裝指南

### 1️⃣ Install OpenCLI Core | 安裝 OpenCLI 核心
First, install the core runtime globally:
首先，請全域安裝核心運行時：

```bash
npm install -g @jackwener/opencli
```

### 2️⃣ Install this Skill | 安裝此技能

#### 📦 For Hermes Agent
```bash
# Use the official skill installer | 使用官方技能安裝程序
hermes skill install https://github.com/cheerhuan/opencli-skill-dev
```

#### 📦 For OpenClaw
```bash
# Use the openclaw skill manager | 使用 OpenClaw 技能管理器
openclaw skill install https://github.com/cheerhuan/opencli-skill-dev
```

---

## 📖 How It Works | 工作原理

This skill implements a standardized high-reliability workflow for creating CLI adapters:
本技能實現了一套標準化的高可靠性工作流，用於創建 CLI 適配器：

> **`Recon (偵察)`** $\longrightarrow$ **`Design (設計)`** $\longrightarrow$ **`Implement (實作)`** $\longrightarrow$ **`Verify (驗證)`**

1. **Recon | 偵察**
   `opencli browser analyze <url>` $\rightarrow$ detect WAF and page patterns.
   使用 `opencli browser analyze <url>` 偵測反爬蟲廠商 (WAF) 與頁面模式。

2. **Design | 設計**
   Map web elements to deterministic CLI arguments.
   將網頁元素映射為確定性的 CLI 參數。

3. **Implement | 實作**
   Write adapters using `wait xhr` for async stability.
   使用 `wait xhr` 編寫適配器，確保異步加載的穩定性。

4. **Verify | 驗證**
   `opencli browser verify` $\rightarrow$ ensure memory persistence and execution success.
   執行 `opencli browser verify` 確保記憶持久化與執行成功。

---

## 🚀 Quick Start for AI Agents | AI Agent 快速上手

Once installed, you can ask your agent:
安裝完成後，您可以直接對您的 Agent 下指令：

> **"Use the `opencli-adapter-dev` skill to help me create a CLI adapter for [Target Website]."**
> **「請使用 `opencli-adapter-dev` 技能幫我為 [目標網站] 建立一個 CLI 適配器。」**

The agent will then autonomously handle the reconnaissance and implementation process.
Agent 將會自主完成從偵察到實作的完整流程。

---

## 📜 License | 授權協議
MIT License. See [LICENSE](LICENSE) for details.
MIT 授權。詳情請參閱 [LICENSE](LICENSE)。
