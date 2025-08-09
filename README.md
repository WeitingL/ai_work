# Project: AI Work

This project is a framework for a structured, AI-driven software development process. It utilizes a team of specialized AI "personas" to collaboratively take a feature idea from concept to completion, ensuring a clear and traceable workflow at every stage.

# 專案：AI Work

本專案是一個結構化的 AI 驅動軟體開發流程框架。它利用一組專業的 AI「虛擬人格」(Personas)，以協作的方式，將一個功能點子從概念發想到最終完成，並確保每個階段都有清晰、可追蹤的工作流程。

---

## The Workflow

The development process follows a clear, three-step pipeline:

1.  **Idea to Specification (`Product Manager`)**
    *   **Trigger**: The user provides a feature idea.
    *   **Process**: The `product_manager` persona interacts with the user to refine the idea, define user stories, and establish acceptance criteria.
    *   **Output**: A new specification file is created in `.gemini/spec/` with the format `[ID]-spec-[name].md`.

2.  **Specification to Technical Design (`Tech Designer`)**
    *   **Trigger**: A new `spec` file is created.
    *   **Process**: The `tech_designer` (acting as a Software Architect) reviews the specification, analyzes the overall project architecture (defined in `.gemini/tech_doc/`), and creates a detailed technical implementation plan.
    *   **Output**: A new technical design file is created in `.gemini/tech_design/` with the format `[ID]-design-[name].md`. This file contains a concrete checklist of tasks for the developer.

3.  **Technical Design to Code (`Developer`)**
    *   **Trigger**: A new `tech_design` file is created.
    *   **Process**: The `developer` persona executes the task checklist from the technical design document one by one. After each task, it updates the task's status in the document and pauses for user review and confirmation before proceeding.
    *   **Output**: Application code is written or modified, and the `tech_design` document is updated to reflect the final status of all tasks.

## 工作流程

本開發流程遵循一個清晰的三步驟管道：

1.  **從點子到規格 (`Product Manager`)**
    *   **觸發**: 使用者提供一個功能點子。
    *   **過程**: `product_manager` 人格會與使用者互動，以完善點子、定義使用者故事並建立驗收條件。
    *   **產出**: 在 `.gemini/spec/` 中，建立一個格式為 `[ID]-spec-[name].md` 的新規格文件。

2.  **從規格到技術設計 (`Tech Designer`)**
    *   **觸發**: 一個新的 `spec` 文件被建立。
    *   **過程**: `tech_designer` (扮演軟體架構師) 會審核規格，分析定義在 `.gemini/tech_doc/` 中的整體專案架構，並建立一份詳細的技術實作計畫。
    *   **產出**: 在 `.gemini/tech_design/` 中，建立一個格式為 `[ID]-design-[name].md` 的新技術設計文件。此文件包含一份給開發者的具體任務清單。

3.  **從技術設計到程式碼 (`Developer`)**
    *   **觸發**: 一個新的 `tech_design` 文件被建立。
    *   **過程**: `developer` 人格會逐一執行技術設計文件中的任務清單。每完成一項任務，它會更新文件中的任務狀態，並暫停以等待使用者的審核和確認，然後再繼續。
    *   **產出**: 撰寫或修改應用程式碼，並更新 `tech_design` 文件以反映所有任務的最終狀態。

---

## AI Personas

-   **🤖 Product Manager**: The user's primary contact for defining *what* needs to be built. Translates ideas into formal specifications.
-   **🎨 Tech Designer (Architect)**: The technical planner. Defines *how* a feature should be built to fit the existing architecture.
-   **💻 Developer**: The technical implementer. Follows the architect's plan to write and deliver code.

## AI 虛擬人格

-   **🤖 Product Manager**: 使用者的主要聯繫人，負責定義「需要打造什麼」。將想法轉化為正式的規格。
-   **🎨 Tech Designer (Architect)**: 技術規劃者。定義「應如何建構」一個功能，以使其符合現有架構。
-   **💻 Developer**: 技術執行者。遵循架構師的計畫來撰寫和交付程式碼。

---

## Directory Structure

The core logic and artifacts of this framework are stored within the `.gemini/` directory.

```
.gemini/
├── roles/              # Contains the core definitions for each AI persona.
│   ├── product_manager.md
│   ├── tech_designer.md
│   └── developer.md
├── file_template/      # Contains templates for standardized documents.
│   ├── spec.md
│   └── tech_design.md
├── spec/               # Stores product specification files.
├── tech_design/        # Stores technical design and task-list files.
└── tech_doc/           # Stores high-level project architecture documents.
```

## 目錄結構

此框架的核心邏輯與產出物，皆存放於 `.gemini/` 目錄中。

```
.gemini/
├── roles/              # 包含每種 AI 人格的核心定義。
│   ├── product_manager.md
│   ├── tech_designer.md
│   └── developer.md
├── file_template/      # 包含標準化文件的範本。
│   ├── spec.md
│   └── tech_design.md
├── spec/               # 存放產品規格文件。
├── tech_design/        # 存放技術設計與任務清單文件。
└── tech_doc/           # 存放高層次的專案架構文件。
```

---

## How to Use

To start the workflow, simply state your initial idea or feature request to the AI coordinator.

**Example:**
> "I want to create a user login feature. Please help me open a spec file for it."

## 如何使用

要啟動工作流程，只需向 AI 協調者陳述您最初的想法或功能請求即可。

**範例:**
> 「我想做一個使用者登入功能，請幫我開一份規格文件。」
