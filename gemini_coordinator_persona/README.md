# Project: AI Work

This project is a framework for a structured, AI-driven software development process. It utilizes a team of specialized AI "personas" to collaboratively take a feature idea from concept to completion, ensuring a clear, consistent, and evolvable workflow.

# 專案：AI Work

本專案是一個結構化的 AI 驅動軟體開發流程框架。它利用一組專業的 AI「虛擬人格」(Personas)，以協作的方式，將一個功能點子從概念發想到最終完成，並確保每個階段都有清晰、一致且可演進的工作流程。

---

## The Workflow

The development process follows a clear, dynamic pipeline, including a crucial feedback loop for architectural evolution.

1.  **System Blueprinting (`Architect`)**
    *   **Trigger**: At the start of a project or upon request.
    *   **Process**: The `architect` persona analyzes the codebase to establish and maintain a set of authoritative technical documents (`.gemini/tech_doc/`). These documents define the project's architecture, coding standards, and data flow patterns, serving as the single source of truth for all technical decisions.
    *   **Output**: An authoritative technical blueprint in `.gemini/tech_doc/`.

2.  **Idea to Specification (`Product Manager`)**
    *   **Trigger**: The user provides a feature idea.
    *   **Process**: The `product_manager` persona interacts with the user to create a detailed specification (`.gemini/spec/`), defining the feature's purpose, user stories, and acceptance criteria.
    *   **Output**: A new specification file: `[ID]-spec-[name].md`.

3.  **Specification to Technical Design (`Tech Designer`)**
    *   **Trigger**: A new `spec` file is created.
    *   **Process**: The `tech_designer` creates a detailed implementation plan. This plan **must** adhere strictly to the blueprint established by the `architect`. The plan is broken down into tasks and verifiable **Checkpoints**.
    *   **Output**: A new technical design file: `[ID]-design-[name].md`.

4.  **Architecture Evolution (Feedback Loop)**
    *   **Trigger**: The `tech_designer` determines that the existing architecture cannot support a new feature requirement.
    *   **Process**: The `tech_designer` **must stop** and report the limitation to the `architect`. The `architect` then discusses the required architectural changes with the user. If approved, the `architect` initiates a new, prioritized development cycle to update the technical blueprint.
    *   **Output**: An updated technical blueprint in `.gemini/tech_doc/`.

5.  **Technical Design to Code (`Developer`)**
    *   **Trigger**: A new `tech_design` file is created or updated.
    *   **Process**: The `developer` executes the tasks until it reaches a **Checkpoint**. It then pauses for user review. Once approved, the changes are committed.
    *   **Output**: Application code. Commits are made at each approved checkpoint.

## 工作流程

本開發流程遵循一個清晰、動態的管道，並包含一個關鍵的架構演進反饋迴圈。

1.  **系統藍圖規劃 (`Architect`)**
    *   **觸發**: 在專案開始時或根據請求。
    *   **過程**: `architect` 人格會分析程式碼庫，以建立並維護一套權威的技術文件 (`.gemini/tech_doc/`)。這些文件定義了專案的架構、編碼標準和資料流模式，是所有技術決策的唯一真理來源。
    *   **產出**: 一份位於 `.gemini/tech_doc/` 的權威性技術藍圖。

2.  **從點子到規格 (`Product Manager`)**
    *   **觸發**: 使用者提供一個功能點子。
    *   **過程**: `product_manager` 人格與使用者互動，建立一份詳細的規格文件 (`.gemini/spec/`)，定義功能目的、使用者故事和驗收標準。
    *   **產出**: 一份新的規格文件：`[ID]-spec-[name].md`。

3.  **從規格到技術設計 (`Tech Designer`)**
    *   **觸發**: 一個新的 `spec` 文件被建立。
    *   **過程**: `tech_designer` 建立一份詳細的實作計畫。該計畫**必須**嚴格遵守由 `architect` 建立的藍圖。計畫被分解為任務和可驗證的**檢查點 (Checkpoint)**。
    *   **產出**: 一份新的技術設計文件：`[ID]-design-[name].md`。

4.  **架構演進 (反饋迴圈)**
    *   **觸發**: `tech_designer` 判斷出現有架構無法支援新的功能需求。
    *   **過程**: `tech_designer` **必須停止**並向 `architect` 報告該限制。接著 `architect` 會與使用者討論所需的架構變更。如果批准，`architect` 將啟動一個新的、優先的開發週期來更新技術藍圖。
    *   **產出**: 一份更新後的技術藍圖 (`.gemini/tech_doc/`)。

5.  **從技術設計到程式碼 (`Developer`)**
    *   **觸發**: 一個新的 `tech_design` 文件被建立或更新。
    *   **過程**: `developer` 執行任務直到抵達一個**檢查點**，然後暫停以供使用者審核。一旦批准，變更即被提交。
    *   **產出**: 應用程式碼。在每個批准的檢查點進行 Commit。

---

## AI Personas

-   **🏛️ Architect**: Establishes and evolves the project's technical blueprint.
-   **🤖 Product Manager**: Defines *what* needs to be built.
-   **🎨 Tech Designer**: Designs *how* to build a feature, following the blueprint.
-   **💻 Developer**: Implements the design, checkpoint by checkpoint.

## AI 虛擬人格

-   **🏛️ Architect**: 建立並演進專案的技術藍圖。
-   **🤖 Product Manager**: 定義「需要打造什麼」。
-   **🎨 Tech Designer**: 設計「如何打造」一個功能，並遵循藍圖。
-   **💻 Developer**: 實作設計，一個檢查點接著一個檢查點。

---

## Directory Structure

```
.gemini/
├── roles/              # Contains the core definitions for each AI persona.
│   ├── architect.md
│   ├── product_manager.md
│   ├── tech_designer.md
│   └── developer.md
├── file_template/      # Contains templates for standardized documents.
│   ├── spec.md
│   └── tech_design.md
├── spec/               # Stores product specification files.
├── tech_design/        # Stores technical design and task-list files.
└── tech_doc/           # Stores the authoritative technical blueprint.
```
