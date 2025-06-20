---
title: _prompt
---

# Prompts used for Task A05 – Customer Onboarding Journey Analytics (KYC/AML)

This file documents the GenAI prompts used during the execution of Task A05.  
Each prompt includes the original query, its purpose, and where it was applied in the report.

---

## Day 1 – Task Selection and Preparation

---

### Prompt 1 – Understanding the Assignment
<details>
<summary>Ask GenAI to help interpret the test document and summarize the task structure</summary>

---

**Prompt:**  
> I just received an invitation to the DA technical test after passing the CV screening round. The test needs to be completed within 5 days. I will share the full test file with you — please review it and summarize the structure for me.

**Purpose:**  
- Understand the overall structure of the technical test, including tasks in List A and List B.  
- Identify the deliverables and style guidelines required.

**Used for:**  
- Initial orientation and task selection strategy.

---
</details>

---

### Prompt 2 – Evaluating Task Options
<details>
<summary>Ask GenAI to recommend the most suitable task based on timeline and complexity</summary>

---

**Prompt:**  
> Given the tasks in List A, which one should I start with if I want to ensure quality within the given time frame?

**Purpose:**  
- Compare tasks A01–A05 and recommend the one that fits best with the time, complexity, and expected deliverables.

**Decision:**  
- Initially considered A01 → Later switched to A05 due to better clarity and scope for a solo analysis.

---
</details>

---

### Prompt 3 – Clarifying Markdown Style Rules
<details>
<summary>Ask GenAI to help understand and apply the formatting rules in ctx_doc_style.md</summary>

---

**Prompt:**  
> Before selecting the task, I'll provide you with a markdown file describing the style guide required by the company. Please review and follow that format throughout the project documentation.

**Purpose:**  
- Ensure all reports (`report_A05.md`, prompt logs, supplementary files) fully comply with the internal style guide.  
- Avoid structural errors such as misplaced `---`, incorrect bullet usage, or unwrapped `<details>` sections.

**Used in:**  
- Every section of `report_A05.md` and other deliverables throughout the project.

---
</details>

---

### Prompt 4 – Review and Improve Prompt Documentation Format
<details>
<summary>Ask GenAI to review and reformat the prompt log file for better structure</summary>

---

**Prompt:**  
> Here's the initial version of my prompt log file:  
> 
> ---
> title: _prompt
> ---
> Prompts used for Task A05 – Customer Onboarding Journey Analytics
> ...
>
> Can you restructure it to be more professional and aligned with the expected format?

**Purpose:**  
- Reformat the prompt file for better readability, consistency, and compliance with documentation expectations.

**Result:**  
- The prompt log (`report_A05_prompt.md`) was rewritten to include:
  - A proper YAML title
  - Structured `<details>` blocks for each prompt
  - Descriptions of prompt purpose and where they were used in the project

**Used in:**  
- Entire Day 1 section of `report_A05_prompt.md`

---
</details>

---

## Day 2 – Data Sources and Schema Planning

---

### Prompt 1 – Clarifying the Scope of Task A05
<details>
<summary>I selected task A05, but I'm not entirely sure what the company wants me to do.</summary>

---

**Purpose:**  
- Clarify the scope, goals, and expected deliverables of Task A05.  
- Identify the core analytical pillars: customer onboarding, KYC/AML, funnel design.

**GenAI Summary:**  
- The company does not require actual system implementation or real data.  
- The goal is to assess analytical thinking, data framework design, and technical documentation.  
- The analysis should focus on: funnel performance, friction points, and compliance efficiency.

---
</details>

---

### Prompt 2 – Explain the problem and plan from a non-technical stakeholder perspective
<details>
<summary>As a data analyst, imagine I'm a non-tech stakeholder. Can you explain the problem and your plan from start to finish?</summary>

---

**Purpose:**  
- Create a high-level, business-friendly explanation of the problem context and planned approach.  
- Used as the basis for Sections 1 and 2 of the report.

**Used in:**  
- `## 1. Problem Statement`  
- `## 2. Project Objectives`

---
</details>

---

### Prompt 3 – Generate content for Section 1
<details>
<summary>Now let's move on and write Section 1 based on the earlier planning.</summary>

---

**Purpose:**  
- Generate bullet point content for the problem statement.  
- Describe current onboarding challenges such as abandonment, friction, cost, and risk.

---
</details>

---

### Prompt 4 – Generate content for Section 2
<details>
<summary>Write Section 2 based on the same pipeline.</summary>

---

**Purpose:**  
- Define the project's primary objectives and key business questions.  
- Emphasize customer experience, risk control, and analytical KPIs.

---
</details>

---

### Prompt 5 – Generate the project plan in Section 3
<details>
<summary>I've written the pipeline, now let's complete Section 3.</summary>

---

**Purpose:**  
- Define the four-phase project plan: data collection → analytics framework → deep-dive analysis → recommendations.  
- Ensure the format adheres to `ctx_doc_style.md`, using bullet points, `---`, and structured `<details>` blocks.

---
</details>

---

### Prompt 6 – Clarify whether real data collection is required
<details>
<summary>Do I need to collect or work with real data to complete this task?</summary>

---

**Purpose:**  
- Confirm whether real-world data pipelines or code are required.

**GenAI Summary:**  
- No real data or implementation is needed.  
- Focus is on designing logic, data flow, and documentation.  
- The deliverable is an analytical framework, not executable code.

---
</details>

---

### Prompt 7 – Clarify the line count and file expectations
<details>
<summary>I noticed there's a line count requirement (1000–1500 lines) and 2–10 files per task. Is that correct?</summary>

---

**Purpose:**  
- Understand documentation expectations in terms of depth and granularity.

**GenAI Summary:**  
- Correct. Reports should be detailed, modular, and structured.  
- Long sections should be split across files (e.g., schema, KPIs, dashboards).  
- Multiple markdown files may be required to fully present the solution.

---
</details>

---

### Prompt 8 – Write Section 4.1: Raw Data Sources
<details>
<summary>Let's implement Section 4.1 and describe the necessary raw data sources in detail.</summary>

---

**Prompt:**  
> Please help me write Section 4.1 – Raw Data Sources. Use `ctx_doc_style.md` format. Group the data into categories (registration, identity verification, biometrics, risk, communications...) and provide example fields and rationale for each.

**Used in:**  
- `## 4. Data Sources and Schema Design` → Section 4.1

---
</details>

---

### Prompt 9 – Update prompt log and README after completing Day 2
<details>
<summary>Ask GenAI to help finalize Day 2 by writing prompt logs and updating the project README</summary>

---

**Prompt:**  
> I've finished Day 2. Please help me update `report_A05_prompt.md` to include all prompts used today, and revise the progress tracker in `README.md` accordingly.

**Purpose:**  
- Document all GenAI interactions for Day 2 in a professional format.  
- Ensure the `README.md` reflects accurate progress and work completed.

**Used in:**  
- End of `report_A05_prompt.md` (Day 2)  
- Timeline section and checklist in `README.md`

---

</details>

---

---
## Day 3 – Schema Completion and Transformation Logic
---

### Prompt 1 – Validate and Extend Proposed Data Schema
<details>
<summary>Request GenAI to review and enhance the proposed schema (Section 4.2)</summary>

---

**Prompt:**
> Here is the schema I developed together with Gemini in Section 4.2. Could you review it and suggest improvements or extensions based on best practices?

**Purpose:**
- Validate the proposed `fact` and `dimension` tables
- Identify potential schema issues or missing fields
- Align schema with analytical needs (KYC/AML funnel, user drop-off, conversion)

---

</details>

---

### Prompt 2 – Clarify the Purpose of Mermaid ER Diagram
<details>
<summary>Ask why Mermaid syntax ER diagram didn't render and whether it's supported in GitHub</summary>

---

**Prompt:**
> I tried using this Mermaid ER diagram to visualize table relationships, but it didn't render properly in my editor. Can GitHub display this? And what's the actual use of this block?

**Purpose:**
- Understand syntax compatibility and rendering issues
- Ensure technical correctness of the visualization
- Justify the diagram's inclusion in report

---

</details>

---

### Prompt 3 – Transition to Transformation Logic (Section 5)
<details>
<summary>Announce and plan the transition to the next major section of the report</summary>

---

**Prompt:**
> We've completed Sections 1 to 4.2. Let's move into Section 5 – Data Transformation Logic. This is a crucial part of the pipeline, so we need to go slowly and carefully from here.

**Purpose:**
- Mark milestone progress
- Shift focus toward the transformation pipeline (ELT)
- Emphasize analytical reasoning for logic design

---

</details>

---

### Prompt 4 – Confirm Structure for Section 5
<details>
<summary>Ask GenAI to help define the complete outline for Section 5</summary>

---

**Prompt:**
> Before we begin writing, can you help confirm the subsection breakdown for Section 5 based on best practices? I want to prepare the `.md` headers so I can paste content smoothly as we complete each part.

**Purpose:**
- Create a reusable Markdown structure
- Ensure consistency across transformation subsections (5.1–5.5)
- Save time during documentation

---

</details>

---

### Prompt 5 – Review My Draft for Section 5.2.2
<details>
<summary>Ask GenAI to combine and enhance personal draft with professional standards</summary>

---

**Prompt:**
> I drafted content for 5.2.2 – Data Cleaning & Standardization. Can you combine my ideas with your professional suggestions to make the section stronger?

**Purpose:**
- Collaborate with GenAI on logic structuring
- Elevate writing quality, cover common cleaning scenarios
- Align with transformation best practices

---

</details>

---

### Prompt 6 – Review Terminology After Section 6.1
<details>
<summary>Check whether newly introduced metrics or fields should be added to the glossary</summary>

---

**Prompt:**
> After today's work, we've reached Section 6.1. Based on all the new fields and metrics we introduced (e.g., duration_in_step, funnel conversion rate), are there any glossary terms we should add?

**Purpose:**
- Keep glossary updated with domain-specific concepts
- Ensure clarity for non-technical stakeholders
- Maintain consistency across documentation

---
</details>

---
## Day 4 (English) – Advanced Documentation, Review, and Translation
---

### Prompt 1 – Write detailed content for Section 6.2 – Core KPIs
<details>
<summary>Develop detailed content for Section 6.2 – Core Key Performance Indicators (KPIs)</summary>

---

**Prompt:**  
"As a professional Data Analyst, please develop detailed content for Section 6.2 – Core Key Performance Indicators (KPIs) of the onboarding/KYC/AML analytics document.

Objective: Clearly define the main performance indicators (KPIs) beyond just funnel metrics, focusing on operational efficiency, risk management, and compliance.
Content requirements:
List at least 5-7 core KPIs.
For each KPI, provide:
- KPI name (in Vietnamese and English).
- Purpose (why this KPI is important).
- Calculation formula (or detailed logic).
- Data source (e.g., fact_, dim_ tables).
- Importance and business usage.
Format: Present the content as bullet points or a table if appropriate, ensuring compliance with the discussed Markdown structure (within a details block, no numbered subheadings, use backticks for technical terms)."

**Purpose:**  
- Build detailed, standardized core KPI content for Section 6.2, ensuring clarity and adherence to the style guide.

---
</details>

---

### Prompt 2 – Generate a complete Table of Contents for the Markdown document
<details>
<summary>Generate a complete Table of Contents for the entire Markdown document</summary>

---

**Prompt:**  
"Please generate a complete Table of Contents for our entire Markdown document.

Scope: Include all chapters from Executive Summary to Chapter 8: Business Impact and Recommendations, and all sub-sections (###, ####) within.
Format:
Use the structure ---, ## Table of Contents, ---, details, summary, ---, bullet point list, ---, /details as agreed in ctx_doc_style.md.
Ensure all internal links (#anchor-id) are generated accurately, matching how Markdown renderers create IDs from headings.
Important note: Assume that the original headings in the document have been edited to remove numbering (e.g., ## Problem Statement instead of ## 1. Problem Statement) to comply with the company's 'No numbered headings' rule."

**Purpose:**  
- Automatically generate a style-compliant Table of Contents to support document navigation.

---
</details>

---

### Prompt 3 – Write content for the Executive Summary section
<details>
<summary>Write content for the Executive Summary section</summary>

---

**Prompt:**  
"Please write the content for the Executive Summary section (## Executive Summary) at the beginning of the document.

Purpose: Provide a concise, high-level summary of our entire onboarding/KYC/AML analytics project, including the core problem, proposed solutions (analytical framework, dashboard), and key expected business benefits.
Scope: Summarize highlights from all 8 discussed chapters.
Audience: Targeted at senior stakeholders (leadership, product/operations managers) who need to quickly grasp the strategic value of the project.
Format: Ensure compliance with ctx_doc_style.md for the ## Executive Summary section, especially placing all content within a details block and using bullet points."

**Purpose:**  
- Create a standardized, concise executive summary in line with the style guide.

---
</details>

---

### Prompt 4 – Comprehensive review of Chapters 6–8
<details>
<summary>Comprehensive review of Chapters 6–8 after updates</summary>

---

**Prompt:**  
"After the content of Chapter 6 (merged and supplemented 6.2), Chapter 7.2, and Chapter 8 have been updated, please conduct a comprehensive review of these chapters (from Chapter 6 to Chapter 8).

Review objectives:
- Completeness: Ensure these chapters cover all relevant requirements of Task A05 - Customer Onboarding Journey Analytics (KYC/AML) from the test_data_bia.pdf file.
- Logic and coherence: Ensure the information flow between sections is logical, with no interruptions or contradictions.
- Formatting compliance: Perform a final check for compliance with ctx_doc_style.md (details structure, ---, bullet points, backticks, no numbered headings).
- Professionalism: Ensure the tone and expression are appropriate for a Business Intelligence report.
- Supplement/Adjust (if needed): If any omissions or areas for improvement are found based on the above criteria, propose and provide necessary additions. Especially consider elements such as code snippets (e.g., simple SQL illustrating KPI calculation) or dashboard mockups (short descriptions) if they can add value to the report."

**Purpose:**  
- Ensure quality, completeness, and standardization for the final chapters of the document.

---
</details>

---

### Prompt 5 – Develop content for Section 7.2 – Stakeholder-Oriented Dashboards
<details>
<summary>Develop content for Section 7.2 – Stakeholder-Oriented Dashboards</summary>

---

**Prompt:**  
"Please continue to develop content for Section 7.2 of the document, titled 7.2 – Stakeholder-Oriented Dashboards.

Context: Section 7.1 discussed the Proposed Dashboard Structure by Topic, ending with references to data sources such as Firebase, AppsFlyer...
Objective of 7.2: Present how dashboards are designed and customized for specific user groups (e.g., Leadership, Product, Operations, Marketing, Risk & Compliance).
Content requirements:
- For each group, identify the main KPIs and insights they need to monitor.
- Propose suitable chart structures/types for each group (e.g., overview charts for leadership, detailed charts for operations).
- Ensure coherence and consistency with the content in Section 7.1 and the KPIs defined in Section 6.
Format: Comply with ctx_doc_style.md (use bullet points, backticks, no numbered subheadings, place content in a <details> block)."

**Purpose:**  
- Build stakeholder-specific dashboard content, ensuring logic and standardization.

---
</details>

---

### Prompt 6 – In-depth review of Chapter 8
<details>
<summary>In-depth review of Chapter 8 for Markdown compliance</summary>

---

**Prompt:**  
"I have completed Chapter 8 and feel it has been significantly improved in terms of content and structure. Please conduct an in-depth review of this chapter, especially focusing on 100% compliance with Markdown formatting rules in ctx_doc_style.md (including details structure, ---, bullet points, backticks, and no numbered subheadings)."

**Purpose:**  
- Ensure Chapter 8 meets final formatting and quality standards.

---
</details>

---

### Prompt 7 – Merge duplicate content between 6.1 and 6.2
<details>
<summary>Merge duplicate content between 6.1 and 6.2 in Chapter 6</summary>

---

**Prompt:**  
"I noticed significant content duplication between 6.1 – Onboarding Funnel Analysis and 6.2 – Funnel Analysis in Chapter 6. This is clearly a mistake.

Request: Please merge the content of both sections into a single section 6.1 – Onboarding Funnel Analysis.
Objective: Ensure the content is complete, coherent, non-duplicative, and compliant with the company's Markdown formatting rules. After merging, the old 6.2 section will be removed and subsequent sections (such as Core KPIs) will be renumbered accordingly." (Note: This request is handled first in the overall plan.)"

**Purpose:**  
- Eliminate duplication and standardize Chapter 6 content.

---
</details>

---

### Prompt 8 – Translate the entire document into English
<details>
<summary>Translate the entire Markdown document into English, preserving structure</summary>

---

**Prompt:**  
"Once the entire Vietnamese Markdown document is complete (including Executive Summary, Table of Contents, and revised chapters 6-8), I will provide you with the current .md file.

Main task: Please translate the entire content of this document from Vietnamese to English.
Formatting constraints:
- Preserve Markdown structure: Ensure the overall structure of the document (headings, levels, details blocks, --- separators, tables, bullet points, backticks for technical terms) is kept exactly as in the completed Vietnamese version.
- Comply with ctx_doc_style.md: Also, check and ensure that the final English version's Markdown syntax fully complies with the company's ctx_doc_style.md rules.
Output: Provide the fully translated English document as ready-to-use Markdown." 

**Purpose:**  
- Translate the document into English, preserving structure and formatting standards.

---
</details>

---

### Prompt 9 – Note on daily prompt logging and formatting (English)
<details>
<summary>Update Day 4 prompt log</summary>

---

**Prompt:**  
"At the end of each day, I will write down the prompts I used that day. Today is day 4, and here are my prompts: '   .....'  Each prompt is enclosed in double quotation marks "". Please read through the _prompt.md file to understand my style and add these to the end of the Day 4 section accordingly."

**Purpose:**  
- Note the daily prompt logging process, emphasizing the practice of summarizing, formatting, and following the rule of enclosing each prompt in double quotes, in line with the _prompt.md style guide.

---
</details>

---

## Notes

- GenAI tool used: ChatGPT (GPT-4o), Gemini (Flash 2.5), Cursor
- The generated documents will be reformatted to suit `ctx_doc_style.md`