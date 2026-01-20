# 🤖 Copilot Studio – Verbatim Knowledge Source Response Pattern

## ✨ Overview

This repository contains an exported **Copilot Studio Agent solution** that demonstrates how to return **verbatim (non-summarized) content from a knowledge source**, while still providing a structured, AI-generated response.

The primary use case is **HR Benefits**, but the pattern is generic and can be reused for any scenario where **exact wording is required** and summarization is not allowed.

---

## Problem Statement

By default, Copilot Studio and AI prompts often **summarize or paraphrase** information retrieved from knowledge sources. In regulated or compliance-sensitive scenarios, this behavior can be problematic.

This solution addresses the need to:

- Preserve **exact policy language**
- Avoid AI summarization or interpretation
- Provide transparency into the **exact source content** used
- Support audit, compliance, and trust requirements

---

## 🏗️ Solution Architecture

The agent is implemented using:

- A knowledge source (HR Benefits)
- Two topics
- A custom AI prompt with strict verbatim rules

### High-Level Flow

1. User submits a query
2. Raw search results are retrieved from the knowledge source
3. AI prompt filters and returns **verbatim quotes only**
4. Response is displayed along with expandable source content

---

## 🖼️ Demo Screenshots (Optional)

> Use this section to visually demonstrate how the **verbatim response pattern** works end-to-end in Copilot Studio.

### Screenshot 1 – AI Prompt Verbatim Instructions

![AI Prompt Verbatim Instructions](./images/AiPrompt.png)

_Description:_ Shows the **AI Prompt instructions** that strictly enforce verbatim quoting, prohibit summarization, and ensure only relevant knowledge source text is returned.

### Screenshot 2 – Initial Agent Response (No Source Shown)

![Initial Agent Response](./images/FirstResponse.png)

_Description:_ Shows the **initial agent response** presented to the user, displaying the formatted answer **without** exposing the underlying knowledge source text.

### Screenshot 3 – Expanded Details with Verbatim Knowledge Source

![Expanded Verbatim Knowledge Source](./images/ExpandedResponse.png)

_Description:_ Shows the response **after the user clicks “Show details”**, where the adaptive card expands to reveal the **exact verbatim quote** from the knowledge source used to generate the answer.

---

## Knowledge Source

- HR Benefits documentation is configured as a Copilot Studio knowledge source
- The solution works with any supported knowledge source and can be easily replaced

---

## 🧩 Topic: `Verbatim`

The **Verbatim** topic is responsible for retrieving **non-summarized content** from the knowledge source.

### Key Components

- **Custom Search Node**
  - Queries the knowledge source
  - Returns raw (non-summarized) results

- **Search Results Variable**
  - Stores the retrieved content exactly as returned
  - Passed downstream without modification

### Purpose

This topic ensures the AI prompt receives **original source text only**, enabling strict verbatim responses.

---

## 🔒 AI Prompt – Verbatim Enforcement

The search results variable is passed into a custom AI prompt designed to **strictly prohibit summarization, paraphrasing, or inference**.

### AI Prompt Instructions

```text
Respond to the user's query using ONLY the search results provided.

CRITICAL RULES:
- You MUST quote search results verbatim.
- You MUST NOT summarize, paraphrase, infer, or add explanations.
- You MUST include ONLY text that directly answers the user query.
- Every quoted sentence MUST explicitly reference the subject of the user query.
- If a sentence is not directly relevant to the user query, DO NOT include it.
- Do NOT include related plans, entities, or descriptions unless they are explicitly asked for.
- If the search results do not contain relevant information, respond with:
  "No relevant information found in the provided search results."

FORMAT:
- Present the answer ONLY as a markdown code block.
- Do not add any text before or after the code block.

#user query: # query
#search results: # search results
```

### Result

- Output contains **only exact quotes** from the knowledge source
- No AI interpretation or hallucination
- Fully auditable and deterministic behavior

---

## 🖼️ Topic: `OnGenerated`

The **OnGenerated** topic is responsible for presenting the final user experience.

### Output Includes

1. **Generated Formatted Response**
   - Clean, user-friendly presentation

2. **Adaptive Card**
   - Includes a button (e.g., "View Source" or "Show Exact Quote")
   - Expanding the card reveals the **verbatim knowledge source text** used

### Benefits

- Improves transparency and trust
- Keeps the UI clean while allowing access to source content
- Enables users to validate responses independently

---

## 🔄 End-to-End User Experience

1. User asks an HR benefits question
2. `Verbatim` topic retrieves raw knowledge source text
3. AI prompt returns exact quotes only
4. `OnGenerated` topic displays:
   - The formatted response
   - An expandable adaptive card with source quotes

---

## ✅ Why This Pattern Matters

- Prevents hallucinations
- Preserves legal and HR wording
- Supports compliance and audit scenarios
- Increases user trust in AI responses
- Suitable for enterprise Copilot deployments

---

## ♻️ Reusability

This pattern is reusable across domains:

- Legal and compliance documentation
- Finance and policy guidance
- Security procedures
- Healthcare or regulated content

You can:

- Swap the knowledge source
- Reuse the AI prompt template
- Reuse the adaptive card pattern

---

## Repository Contents

- Exported Copilot Studio solution
- Topics:
  - `Verbatim`
  - `OnGenerated`

- AI prompt configuration
- Adaptive card definition

---

## 🚀 Getting Started

1. Import the solution into Copilot Studio
2. Configure or replace the knowledge source
3. Review the AI prompt instructions (optional)
4. Publish the agent

---

## 📄 License & Usage

This repository is provided as a **reference implementation** and can be adapted or extended by customers and internal teams.
