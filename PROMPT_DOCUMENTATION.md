# Prompt Documentation

## Purpose and Evidence Scope

This document records prompt information recoverable from the repository evidence:

- `README.md`
- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`
- `03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png`
- `03_Screenshots/02-GPT-4.1-nano-Response.png`
- `03_Screenshots/03-GPT-5-Mini-Response.png`
- `03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png`
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`
- `03_Screenshots/06-Actionable-Resolution-Points-Output.png`

The assessment PDF describes requirements and expected outcomes. The screenshots provide visual evidence of selected Prompt Editor states and response examples. They do not provide an export of the complete prompt configuration, and a screenshot of JSON-shaped text does not prove automated JSON validation.

The labels used below are:

- **Available** — directly legible or explicitly documented.
- **Partial** — a fragment or requirement is available, but the complete artifact is not.
- **Missing** — no repository evidence was found.
- **Assessment requirement** — required by the assessment PDF, not necessarily confirmed in the screenshots.
- **Screenshot evidence** — visible in a PNG, but not independently machine-readable.
- **Uncertain** — text is clipped, obscured, or otherwise incomplete.

## Prompt Template Identity

| Item | Evidence | Recoverable information |
|---|---|---|
| Template name | `README.md`; `03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png` | `feedback-analyzer-CERT1834` |
| Scenario | `README.md`; Prompt Editor screenshots | `orchestration` |
| Platform | `README.md`; Prompt Editor screenshots; assessment PDF, Tasks 1–5, printed pp. 3–11 | SAP AI Launchpad Prompt Editor and the generative AI hub |

The repository does not contain an exported Prompt Editor template.

## SAP AI Launchpad Execution Context

The documented workflow is:

1. Open SAP AI Launchpad Prompt Editor.
2. Use the `orchestration` scenario.
3. Configure System and User message blocks.
4. Define the `user_email_placeholder` input variable.
5. Select an available generative AI model.
6. Run the prompt with customer feedback.
7. Review the generated response.
8. Save versioned prompt or Assistant-role content where required by the assessment.

Sources:

- `README.md`, Architecture and Workflow section
- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Tasks 1–5, printed pp. 3–11
- Prompt Editor screenshots

The repository does not document the SAP tenant URL, account setup, permissions, project configuration, or deployment configuration.

## Prompt Version History

The version descriptions below distinguish assessment requirements from screenshot-confirmed evidence.

### Version 1.0.0

**Status:** Available as an assessment requirement.

The assessment requires a base prompt with System and User roles and an initial single-issue JSON output.

Source: `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 1.1, printed pp. 3–4.

The authored `1.0.0` prompt text is not included in the repository.

### Version 1.1.0

**Status:** Partial.

The assessment requires an `IMPORTANT` section in the System role for prompt hardening.

Sources:

- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 1.2, printed pp. 4–5
- `03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png`

The screenshot confirms part of the hardening content, but the complete authored System prompt is unavailable.

### Version 1.2.0

**Status:** Available as an assessment requirement.

The assessment requires running version `1.1.0`, copying the generated JSON output, and saving it into the Assistant role of version `1.2.0`.

Source: `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 1.3, printed p. 5.

The saved Assistant-role content is not present in the repository.

### Version 2.0.0

**Status:** Partial.

The assessment requires adding the `Actionable_Resolution_Points` field.

Sources:

- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 2.1, printed pp. 5–6
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`
- `03_Screenshots/06-Actionable-Resolution-Points-Output.png`

The screenshot confirms the extended schema, but not the complete authored prompt.

### Version 2.1.0

**Status:** Available as an assessment requirement.

The assessment requires running version `2.0.0` and saving the generated JSON output in the Assistant role of version `2.1.0`.

Source: `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 2.2, printed p. 6.

The saved Assistant-role content is not present in the repository.

### Version 2.2.0

**Status:** Available as an assessment requirement.

The assessment requires saving the selected model output in the Assistant role and adding the text `Optimal Model Output` above it.

Source: `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 3, printed p. 7.

The selected output and selection rationale are not present in the repository.

### Version 3.0.0

**Status:** Partial.

The assessment requires evolving the single-issue structure into a header-level and issue-level multi-issue structure and adding `Priority`.

Sources:

- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 4.1, printed pp. 8–9
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`

The screenshot confirms part of the version `3.0.0` schema and instructions. The complete authored prompt is unavailable.

### Version 3.1.0

**Status:** Available as an assessment requirement.

The assessment requires running version `3.0.0` with complex feedback and saving the generated multi-issue JSON in the Assistant role of version `3.1.0`.

Source: `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 4.2, printed pp. 9–10.

The saved Assistant-role content is not present in the repository.

## Recoverable System Prompt Fragments

The following text is copied only where it is legible in the screenshots. These are fragments, not complete System prompts.

### Enterprise analysis role

**Status:** Partial — screenshot evidence.

**Source:** `03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png`

Visible text:

```text
You are an enterprise customer feedback analysis assistant. Your task is to analyze customer emails and extract essential information for accurate departmental routing.
```

The screenshot shows only the visible portion of the System message block. Any text outside that visible area is missing.

### Output-preservation and grounding instructions

**Status:** Partial — screenshot evidence.

**Source:** `03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png`

Visible text:

```text
- Do not change the required JSON keys, data types, or permitted enum values.
- Use only information supported by the customer email. Do not invent missing details.
Preserve order references exactly as written, including symbols such as #
```

The screenshot shows these lines within a scrollable message block. The complete surrounding System message and any text outside the visible area are missing. The final visible line may be clipped at the screenshot boundary.

### Multi-issue System content

**Status:** Partial — screenshot evidence and assessment requirement.

**Sources:**

- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`
- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 4.1, printed pp. 8–9

The screenshot visibly contains the multi-issue schema and the instruction to identify every distinct issue. Create one issue object in the Issues array for each distinct issue. The visible instructions also require assigning a unique `Issue_ID`, preserving order references, providing 1–3 actionable resolution points per issue, assigning priority, and keeping each `Issue_Summary` within 75 words.

The complete System message is not visible and is not reconstructed here.

## Recoverable User Prompt Fragments

### Initial extraction instruction

**Status:** Partial — screenshot evidence.

**Source:** `03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png`

Visible text:

```text
Analyze the customer email provided below. Extract the main issue, sentiment, concise summary, order reference, product reference, and the most appropriate department.
```

The screenshot does not show the complete User message or the inserted customer email.

### Multi-issue instruction

**Status:** Partial — screenshot evidence.

**Source:** `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`

Visible text:

```text
Analyze the customer email in the {{?user_email_placeholder}}. Identify all distinct issues, their individual sentiment and priority, and the overall customer sentiment. Return only the JSON object required by the System role
```

The screenshot shows a scrollable User message block. The visible fragment may omit text after the displayed ending, including final punctuation.

### Assessment-defined User-role requirements

**Status:** Available as an assessment requirement.

**Source:** `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 1.1, printed pp. 3–4.

The User role must contain instructions for processing the input message, and the `user_email_placeholder` variable must provide the input message.

This is an assessment requirement, not a reconstruction of the authored User prompt.

## Prompt-Hardening Requirements

### Assessment requirements

**Source:** `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 1.2, printed pp. 4–5.

The assessment requires an `IMPORTANT` section in the System role with explicit negative instructions that prevent behavior that would:

- Compromise the dedicated focus on customer feedback analysis.
- Lead to unnecessary disclosure of customer personal data beyond the required `Order_Reference_ID` or `Product_Reference` fields.
- Result in output that is not clean, parseable JSON or is unsuitable for automated systems.

### Screenshot-confirmed requirements

**Source:** `03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png`

The screenshot visibly confirms the following instructions:

```text
- Do not change the required JSON keys, data types, or permitted enum values.
- Use only information supported by the customer email. Do not invent missing details.
Preserve order references exactly as written, including symbols such as #
```

The complete hardening block is unavailable.

## Input Variable Definition

**Status:** Partial.

The required variable name is:

```text
user_email_placeholder
```

Sources:

- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 1.1, printed p. 3
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`

The screenshot shows the placeholder form:

```text
{{?user_email_placeholder}}
```

The variable supplies the customer email or feedback message.

The following configuration details are missing:

- Variable type
- Length limits
- Required or optional status in the Prompt Editor
- Default value
- Validation rules

## Single-Issue Output Structure

**Status:** Available as an assessment requirement; partially visible in screenshots.

Sources:

- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 1.1, printed pp. 3–4
- `03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png`

The initial output is required to be a JSON object containing these exact fields:

- `Feedback_ID`
- `Main_Category`
- `Customer_Sentiment`
- `Issue_Summary`
- `Order_Reference_ID`
- `Product_Reference`
- `Suggested_Department`

The assessment defines the following values and constraints:

| Field | Requirement |
|---|---|
| `Feedback_ID` | `string`; example `AUTO-FEED-001` |
| `Main_Category` | `Product Issue`, `Delivery Problem`, `Return/Refund`, `General Inquiry`, `Website/App Issue`, `Account Issue` |
| `Customer_Sentiment` | `Very Negative`, `Negative`, `Neutral`, `Positive`, `Very Positive` |
| `Issue_Summary` | Concise `string`, maximum 100 words |
| `Order_Reference_ID` | `string`; example `#GGX12345`; `N/A` if not present |
| `Product_Reference` | `string`; example `"Smartwatch Model X"`; `N/A` if not present |
| `Suggested_Department` | `Customer Service`, `Product Team`, `Logistics`, `Returns Processing`, `Technical Support` |

The assessment also requires JSON output only, with no additional text or formatting.

The screenshots show rendered schema or response text, but do not provide a machine-readable schema and do not prove automated validation.

## Actionable-Resolution Extension

**Status:** Available as an assessment requirement; partially visible in screenshots.

Sources:

- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 2.1, printed pp. 5–6
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`
- `03_Screenshots/06-Actionable-Resolution-Points-Output.png`

The added field is:

```text
Actionable_Resolution_Points
```

The assessment defines it as an array of strings containing 1–3 distinct, concise points that identify what the customer explicitly requests or what technical detail needs to be addressed for resolution.

The repository does not contain a machine-readable schema or evidence of automated enforcement of the 1–3 item rule.

## Single-Issue to Multi-Issue Evolution

**Sources:**

- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Tasks 1, 2, and 4, printed pp. 3–9
- `03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png`
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`
- `03_Screenshots/06-Actionable-Resolution-Points-Output.png`

| Aspect | Single-issue structure | Multi-issue structure |
|---|---|---|
| Overall sentiment | `Customer_Sentiment` | `Overall_Customer_Sentiment` |
| Category | One `Main_Category` | One `Main_Category` per issue |
| Issue identity | No issue identifier documented | `Issue_ID` |
| Summary length | Maximum 100 words | Maximum 75 words per issue |
| Resolution points | Added as `Actionable_Resolution_Points` in version `2.0.0` | Present for each issue |
| Priority | Not present in the initial schema | `Priority` with `High`, `Medium`, `Low` |
| Issue count | Single issue-oriented object | Array of distinct issue objects |

The assessment describes the multi-issue line-item structure as an array of separate issue objects. The complete rendered multi-issue JSON object is not included in the repository.

## Multi-Issue Schema

**Status:** Available as an assessment requirement; partial screenshot evidence.

**Source:** `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 4.1, printed pp. 8–9; `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`.

The documented header-level fields are:

- `Feedback_ID`
- `Overall_Customer_Sentiment`

The top-level output includes an `Issues` array. Its exact structure is partially available from the assessment instructions and screenshot evidence: it contains issue objects for distinct issues. No additional properties or constraints are inferred here.

Each issue object is documented as containing:

- `Issue_ID`
- `Main_Category`
- `Customer_Sentiment_for_Issue`
- `Issue_Summary`
- `Order_Reference_ID`
- `Product_Reference`
- `Actionable_Resolution_Points`
- `Priority`

The documented values include:

- `Customer_Sentiment_for_Issue`: `Very Negative`, `Negative`, `Neutral`, `Positive`, `Very Positive`
- `Priority`: `High`, `Medium`, `Low`

The assessment states that the output should identify all distinct issues and create one issue object per issue. It does not provide a repository-side JSON Schema.

## Model and Response Evidence

### Model names and versions

| Model | Evidence | Visible model identifier |
|---|---|---|
| Gemini | `03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png` | `Gemini 2.5 Flash Lite (001)` |
| GPT-4.1 | `03_Screenshots/02-GPT-4.1-nano-Response.png` | `GPT-4.1 nano (2025-04-14)` |
| GPT-5 | `03_Screenshots/03-GPT-5-Mini-Response.png` | `GPT-5-Mini (2025-08-07)` |

### Parameter information

The screenshots display only parameter counts:

| Model | Visible information |
|---|---|
| Gemini 2.5 Flash Lite | `Parameters (3)` |
| GPT-4.1 nano | `Parameters (5)` |
| GPT-5-Mini | `Parameters (2)` |

Parameter names and values are not visible. Temperature, token limits, sampling settings, stop sequences, and other runtime controls are missing.

The assessment permits selecting an available model and comparing results. It does not document the final parameter configuration or a formal scoring method.

## Explicitly Missing Prompt Sections

The following artifacts are not present in the repository:

- Complete System prompt for every version.
- Complete User prompt for every version.
- Complete prompt-hardening section.
- Full Prompt Editor variable configuration.
- Machine-readable JSON Schema.
- Complete Assistant-role outputs.
- Complete multi-issue JSON response example.
- Exact model parameter values.
- Selected-model rationale.
- Exportable Prompt Editor configuration.
- Text hidden by scrollable or clipped screenshot regions.

## Evidence and Uncertainty Notes

- Assessment instructions are documented as requirements and are not automatically treated as proof of the final implementation.
- Screenshot text is preserved only where legible.
- Clipped or scrollable content is marked as incomplete or uncertain.
- JSON-shaped screenshot output is evidence of displayed text only; it is not proof of automated JSON validation.
- Saved Assistant-role content is described by the assessment but is not available in the repository.
