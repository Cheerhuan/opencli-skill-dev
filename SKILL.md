---
name: opencli-adapter-dev
description: 使用 OpenCLI 將網頁或 Electron App 轉化為標準化 CLI 適配器 (Adapter) 的開發流程。
category: software-development
---

# OpenCLI Adapter 開發指南

本技能定義了將任何網站或桌面應用程式轉化為 deterministic CLI 接口的標準作業流程。核心理念是「先偵察 $\rightarrow$ 後定義 $\rightarrow$ 實作 $\rightarrow$ 驗證」。

## 觸發條件
- 用戶要求為某個網站或 App 建立 CLI 指令。
- 需要將現有的瀏覽器工作流轉化為可由 AI Agent 調用的工具。

## 核心原語
- `opencli browser analyze <url>`: 快速偵察頁面模式 (Pattern) 與反爬蟲廠商 (WAF)。
- `opencli browser wait xhr <regex>`: 等待特定 API 回傳，解決 SPA 異步加載問題。
- `opencli browser verify`: 驗證適配器邏輯是否正確執行且狀態寫回記憶。

## 標準開發流程

### 階段 1：初步偵察 (Reconnaissance)
1. **分析頁面屬性**：
   執行 `opencli browser analyze <url>`。
   - 識別頁面模式 (A/B/C/D)。
   - 確認反爬蟲供應商 (如 Cloudflare, Akamai)。
   - 決定最適合的適配路徑。

2. **交互映射**：
   使用 `opencli browser` 原始指令嘗試手動觸發目標動作（點擊、輸入），記錄正確的 CSS Selector 或 XPath。

### 階段 2：適配器設計 (Design)
1. **定義指令集**：
   確定該適配器需要提供哪些命令（例如：`search`, `get-detail`, `post-comment`）。
2. **參數映射**：
   將 CLI 參數映射到頁面的輸入欄位或 API 請求參數。

### 階段 3：實作與編碼 (Implementation)
1. **撰寫適配邏輯**：
   依照 OpenCLI 規範編寫適配器代碼。
2. **引入強健性檢查 (Fixtures)**：
   - 使用 `mustNotContain` 捕捉內容污染。
   - 使用 `mustBeTruthy` 避免 `|| 0` 或 `|| false` 的靜默失敗。
   - 優先使用 `wait xhr` 而非固定 `wait time N`。

### 階段 4：驗證與迭代 (Verify & Iterate)
1. **執行驗證**：
   運行 `opencli browser verify`。
2. **故障診斷**：
   - 若驗證失敗，檢查 `~/.opencli/sites/` 是否正確寫回記憶。
   - 使用 `--strict-memory` 模式強制檢查記憶持久化。
3. **優化**：
   根據失敗模式收緊適配器邏輯，而非放寬驗證條件。

## 常見陷阱與對策 (Pitfalls)
- **靜默失敗 (Silent Failure)**：頁面顯示成功但數據未提取。$\rightarrow$ *對策：增加 Fixture 內容檢查*。
- **WAF 攔截**：突然出現驗證碼或 403。$\rightarrow$ *對策：檢查 `browser analyze` 的供應商建議，調整 Header 或使用 Session 保持*。
- **DOM 漂移**：網站更新導致 Selector 失效。$\rightarrow$ *對策：使用更具語義化的 Selector 或相對路徑*。

## 驗證清單
- [ ] `opencli browser analyze` 已確認頁面模式。
- [ ] 所有關鍵路徑均使用 `wait xhr` 確保確定性。
- [ ] 已通過 `opencli browser verify` 驗證。
- [ ] 記憶狀態能正確持久化至本地文件。
