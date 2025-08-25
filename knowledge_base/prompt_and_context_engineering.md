# Knowledge Area: Prompt and Context Engineering

## 1. Core Concepts

### Zero-Shot Prompting (零樣本提示)
*   **核心思想**: 我們相信 AI 模型在它龐大的訓練資料中，已經「學會」了執行某些任務的潛在能力。因此，我們不提供任何範例，而是直接下達指令，看看它是否能「零學習」就直接完成任務。
*   **一個比喻**: 就像您對一位經驗豐富的廚師說：「請做一道番茄炒蛋。」您不會附上食譜，因為您相信他懂。
*   **使用者初步理解**: 直接請 Agent 自行處理，不給予範例。

### Few-Shot Prompting (少樣本提示)
*   **核心思想**: 當任務比較複雜、需要特定格式，或 AI 不太確定我們想要什麼時，我們會給它一或多個完整的「指令 -> 答案」範例，讓它能更精準地模仿出我們想要的結果。
*   **一個比喻**: 您對一位廚師說：「我想請你做一道菜。例如，『輸入：雞蛋、青蔥』，你就要『輸出：青蔥炒蛋』。現在，如果『輸入：雞蛋、番茄』，你該怎麼做？」
*   **使用者初步理解**: 給予範例，請 agent 依樣畫葫蘆。

### Chain of Thought (CoT) Prompting (思維鏈提示)
*   **核心思想**: 它是 Few-shot 提示的一種「升級版」。在 CoT 中，我們給的是「問題 -> 推理步驟 -> 答案」的範例，而不僅僅是「問題 -> 答案」。
*   **目的**: 我們不只教 AI「答案是什麼」，更重要的是教它「如何思考」，引導它在回答時模仿這種有條理的推理模式。這對於需要邏輯、數學或多步驟規劃的任務特別有效。
*   **使用者初步理解**: 提供思維的順序或是方式，讓 Agent 依照一個流程進行。

---

## 2. Key Principles

### 1. Managing Context Drift (情境漂移管理)
*   **核心問題**: AI 的「記憶體」(Context Window) 有限。如果沒有管理，對話過程中的無用細節、重複資訊或中間錯誤會不斷累積（情境雪球效應），稀釋重要指令的權重，導致 AI「分心」並偏離原始目標。
*   **使用者初步理解**: Agent 在過程中會累積很多 context 資訊，且 user 無法中斷或確認，因此結果很容易被帶偏。
*   **解決策略 (Context Engineering)**:
    *   **情境總結 (Summarization)**: 定期將長篇對話濃縮成摘要。
    *   **情境過濾 (Filtering)**: 主動移除無關或過時的資訊。
    *   **結構化情境 (Structured Context)**: 使用 JSON、XML 或清晰的分隔符來組織資訊，幫助 AI 定位。
    *   **使用者檢查點 (User Checkpoints)**: 在關鍵步驟後強制 AI 暫停，尋求使用者確認，避免錯誤累積。

### 2. Defining Context (情境的具體定義)
*   **核心概念**: 「情境」是 AI 在回答問題時所能「看到」的全部資訊，是其唯一的「短期記憶」。
*   **組成部分**:
    *   **系統提示 (System Prompt)**: 定義 AI 的角色和能力 (e.g., `GEMINI.md`)。
    *   **對話歷史 (Conversation History)**: 從頭到尾的所有來回對話。
    *   **工具輸出 (Tool Outputs)**: AI 使用工具後返回的結果。

### 3. Structured Prompting / "Note-Taking" (結構化提示 / 做筆記法)
*   **核心思想**: 與其給 AI 一大段雜亂的文字，不如使用結構化的格式（如 Markdown, XML, JSON）來組織提示，幫助 AI 更清晰地理解意圖。
*   **一個比喻**: 這就像是給 AI 一份條理分明的講義，而不是一堆雜亂的草稿。

### 4. Interaction Philosophy (互動理念)
*   **核心思想**: 將與 AI 的關係，從「操作員 vs. 工具」轉變為「老師 vs. 學生」或「經理 vs. 新進員工」的思維模式。
*   **實踐方法**:
    *   **給予清晰的身份 (Persona)**。
    *   **提供明確的目標 (Goal)**。
    *   **展示好的範例 (Exemplars)**。
    *   **引導與修正 (Guidance & Feedback)**。

---

## 3. Examples

*(You can add concrete examples of prompts or context strategies mentioned.)*

---

## 4. Summary & Source

This note is based on the following YouTube video.

*   **Video Title**: AI 提示词工程上下文工程15分钟弄懂！
*   **Summary**: The video explains AI Prompt Engineering and Context Engineering in 15 minutes. It covers topics such as what prompts are, prompt engineering, context, managing context length, and the philosophy behind it.
*   **URL**: https://www.youtube.com/watch?v=-8Ygq9AVWZ8

---
