---
name: Design System Pro
description:
  建立具備可擴展性的設計系統模型。專注於三層 Token 架構、CSS 變數管理與組件狀態規範。
---

# UI UX Pro Max - 設計系統 (Design System)

當需要「建立設計規範」、「定義 Token」或「設定 Tailwind 主題」時使用。

## 🏗️ 三層 Token 架構

設計系統的核心在於將硬編碼的值轉化為具備語義的變數：

1.  **原始層 (Primitive)**：定義具體的顏色數值。
    *   `--color-blue-600: #2563EB;`
2.  **語義層 (Semantic)**：定義顏色的用途。
    *   `--color-primary: var(--color-blue-600);`
3.  **組件層 (Component)**：為特定組件定義屬性。
    *   `--button-bg: var(--color-primary);`

## 🎨 組件規範模式 (Spec Pattern)

定義組件時，應明確規範各種狀態：

| 屬性 | 預設 (Default) | 懸停 (Hover) | 點擊 (Active) | 禁用 (Disabled) |
| :--- | :--- | :--- | :--- | :--- |
| **背景色** | primary | primary-dark | primary-darker | muted |
| **文字顏色** | white | white | white | muted-fg |
| **陰影** | sm | md | none | none |

## 🛠️ 技術整合最佳實踐

*   **Tailwind 整合**：將 Semantic Tokens 對應到 `tailwind.config.js` 的 `theme.extend`。
*   **深色模式**：只需更換語義層 (Semantic) 的變數值，組件層 (Component) 即可自動更新。
*   **HSL 格式**：色彩 Token 建議使用 HSL 格式，方便在 CSS 中靈活調整透明度。

## 🛡️ 核心原則
1.  **嚴禁硬編碼**：組件代碼中絕對不可出現 Hex 色值，必須引用變數。
2.  **文件化**：每一個 Token 的用途都應被文件化及註解。
3.  **原子化**：從最小的元素（顏色、間距、字體）向上構建組件。
