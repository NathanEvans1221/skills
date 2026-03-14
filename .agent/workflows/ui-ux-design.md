---
description: 如何使用 UI UX Pro Max 技能組進行產品設計與系統生成
---

# UI UX Pro Max 設計工作流

本工作流指導 AI 如何利用 `ui-ux-pro-max` 的數據與腳本，從零開始構思並生成一個專業的設計系統。

## 1. 需求分析與產品定義
首先，根據使用者的產品描述，識別產品類型與核心目標。
// turbo
- 使用 `search.py` 搜尋相關產品範例：
  ```powershell
  python d:\github\chiisen\skills\ui-ux-pro-max\scripts\search.py "<產品描述>" --domain product
  ```

## 2. 生成設計系統提案
基於識別到的產品類型，生成完整的設計提案（包含配色、字體、風格、佈局模式）。
// turbo
- 執行自動化生成指令（建議使用 Markdown 格式）：
  ```powershell
  python d:\github\chiisen\skills\ui-ux-pro-max\scripts\search.py "<產品描述>" --design-system --format markdown
  ```

## 3. 持久化設計規範 (Source of Truth)
將確定的設計規範保存到專案目錄中，以便後續開發參考。
// turbo
- 執行持久化指令：
  ```powershell
  python d:\github\chiisen\skills\ui-ux-pro-max\scripts\search.py "<產品描述>" --design-system --persist --project-name "<專案名稱>"
  ```

## 4. 針對特定頁面進行微調 (Overrides)
如果需要開發特定頁面（如 Dashboard, Checkout），應生成對應的覆寫規則。
// turbo
- 針對特定頁面執行：
  ```powershell
  python d:\github\chiisen\skills\ui-ux-pro-max\scripts\search.py "<產品描述>" --design-system --persist --project-name "<專案名稱>" --page "<頁面名稱>"
  ```

## 5. UI/UX 準則檢核
在編寫代碼前，請務必查閱相關的 UX 與效能優化準則。
- 查詢 UX 準則：`python ...search.py "<關鍵字>" --domain ux`
- 查詢 React 效能：`python ...search.py "<關鍵字>" --domain react`
- 查詢字體配對：`python ...search.py "<關鍵字>" --domain typography`

## 6. 完工與驗收
交付程式碼後，請執行 `ui-ux-pro-max` 提供的 **Pre-Delivery Checklist** 進行自我檢核。
