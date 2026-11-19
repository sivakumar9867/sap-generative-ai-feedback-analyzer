# Output Schema Documentation

## Purpose and Evidence Scope

This document records output-structure information explicitly available from:

- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`
- `PROMPT_DOCUMENTATION.md`
- `03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png`
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`
- `03_Screenshots/06-Actionable-Resolution-Points-Output.png`

The assessment PDF defines requirements. The screenshots show selected Prompt Editor schema and response views. Screenshot evidence is not proof of automated JSON parsing or validation.

The following status labels are used:

- **Assessment requirement** — explicitly required by the assessment PDF.
- **Screenshot evidence** — visible in a screenshot.
- **Partial** — only part of the structure or constraint is available.
- **Missing** — no repository evidence is available.

No machine-readable JSON Schema or guessed JSON examples are included.

## Initial Single-Issue Structure

**Status:** Available as an assessment requirement; partially visible in screenshot evidence.

The initial output is required to be a JSON object containing these seven fields:

1. `Feedback_ID`
2. `Main_Category`
3. `Customer_Sentiment`
4. `Issue_Summary`
5. `Order_Reference_ID`
6. `Product_Reference`
7. `Suggested_Department`

Sources:

- Assessment PDF, Task 1.1, printed pp. 3–4
- `PROMPT_DOCUMENTATION.md`, “Single-Issue Output Structure”
- `03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png`

The assessment also requires JSON output only, with no additional text or formatting.

## Single-Issue Field Definitions

| Field | Explicit data type or requirement | Allowed values or representation | Evidence | Status |
|---|---|---|---|---|
| `Feedback_ID` | `string` | No allowed-value list documented | Assessment PDF, Task 1.1, printed p. 3 | Available |
| `Main_Category` | `enum` | `Product Issue`; `Delivery Problem`; `Return/Refund`; `General Inquiry`; `Website/App Issue`; `Account Issue` | Assessment PDF, Task 1.1, printed pp. 3–4 | Available |
| `Customer_Sentiment` | `enum` | `Very Negative`; `Negative`; `Neutral`; `Positive`; `Very Positive` | Assessment PDF, Task 1.1, printed p. 4 | Available |
| `Issue_Summary` | `string` | Maximum 100 words | Assessment PDF, Task 1.1, printed p. 4 | Available |
| `Order_Reference_ID` | `string` | `N/A` if not present | Assessment PDF, Task 1.1, printed p. 4 | Available |
| `Product_Reference` | `string` | `N/A` if not present | Assessment PDF, Task 1.1, printed p. 4 | Available |
| `Suggested_Department` | `enum` | `Customer Service`; `Product Team`; `Logistics`; `Returns Processing`; `Technical Support` | Assessment PDF, Task 1.1, printed pp. 4 | Available |

The assessment provides examples for `Feedback_ID`, `Order_Reference_ID`, and `Product_Reference`, but those examples are not reproduced here as output fixtures.

`N/A` is documented only for missing `Order_Reference_ID` and `Product_Reference`. No other field is assigned an `N/A` representation by the available evidence.

## Single-Issue Evidence Versus Constraints

The assessment explicitly defines the fields, data types, enums, and summary limit above. Screenshot 04 shows rendered schema and prompt content that correspond to the single-issue structure.

The screenshot does not establish:

- A machine-readable JSON Schema.
- Additional-property rules.
- Nullability rules.
- Pattern validation for IDs or references.
- Automated enforcement of the 100-word limit.
- Automated JSON parsing or validation.

## Actionable Resolution Extension

**Status:** Available as an assessment requirement; partially visible in screenshot evidence.

The field added in prompt version `2.0.0` is:

```text
Actionable_Resolution_Points
```

The assessment defines this field as an array of strings containing 1–3 distinct, concise points that identify what the customer explicitly requests or what technical detail needs to be addressed for resolution.

Sources:

- Assessment PDF, Task 2.1, printed pp. 5–6
- `PROMPT_DOCUMENTATION.md`, “Actionable-Resolution Extension”
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`
- `03_Screenshots/06-Actionable-Resolution-Points-Output.png`

The available evidence does not define additional array constraints or prove automated enforcement of the 1–3 item requirement.

## Multi-Issue Header Structure

**Status:** Partial.

The assessment describes a two-level JSON structure:

- A header level.
- A line-item level containing distinct customer issues.

The documented header-level fields are:

- `Feedback_ID`
- `Overall_Customer_Sentiment`

Sources:

- Assessment PDF, Task 4.1, printed pp. 8–9
- `PROMPT_DOCUMENTATION.md`, “Multi-Issue Schema”
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`

The available evidence does not explicitly define data types or additional constraints for these header fields. The initial single-issue constraints are not automatically applied here unless separately documented.

## Top-Level `Issues` Array

**Status:** Partial.

The multi-issue output includes a top-level `Issues` array. Its exact structure is only partially available from the assessment instructions and screenshot evidence.

The available evidence supports the following statement:

> The `Issues` array contains one issue object for each distinct issue.

Sources:

- Assessment PDF, Task 4.1, printed pp. 8–9
- `PROMPT_DOCUMENTATION.md`, “Multi-Issue Schema”
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`

The repository does not provide a complete machine-readable definition of the array or additional array constraints.

## Multi-Issue Issue-Level Fields

Each issue object is documented as containing these eight fields:

1. `Issue_ID`
2. `Main_Category`
3. `Customer_Sentiment_for_Issue`
4. `Issue_Summary`
5. `Order_Reference_ID`
6. `Product_Reference`
7. `Actionable_Resolution_Points`
8. `Priority`

Source:

- Assessment PDF, Task 4.1, printed pp. 8–9
- `PROMPT_DOCUMENTATION.md`, “Multi-Issue Schema”
- `03_Screenshots/05-Multi-Issue-Extraction-Prompt.png`

### `Issue_ID`

- Assessment requirement: `string`.
- Intended to identify each distinct issue.
- The assessment gives identifier examples, but no repository-side uniqueness validation is available.

### `Main_Category`

- Assessment requirement: `enum`.
- Allowed values:
  - `Product Issue`
  - `Delivery Problem`
  - `Return/Refund`
  - `General Inquiry`
  - `Website/App Issue`
  - `Account Issue`

The assessment explicitly states that this uses the same category values as before.

### `Customer_Sentiment_for_Issue`

- Assessment requirement: `enum`.
- Allowed values:
  - `Very Negative`
  - `Negative`
  - `Neutral`
  - `Positive`
  - `Very Positive`

### `Issue_Summary`

- Assessment requirement: `string`.
- Maximum 75 words for each issue summary.

### `Order_Reference_ID`

- Assessment requirement: `string`.
- `N/A` if not present.
- Specific to the issue.

### `Product_Reference`

- Assessment requirement: `string`.
- `N/A` if not present.
- Specific to the issue.

### `Actionable_Resolution_Points`

- Assessment requirement: array of strings.
- Contains 1–3 distinct, concise points for the issue.

### `Priority`

- Assessment requirement: `enum`.
- Allowed values:
  - `High`
  - `Medium`
  - `Low`
- The assessment describes priority as based on urgency, impact, and severity of the specific issue.

The evidence does not define a deterministic priority-scoring formula.

## Single-Issue Versus Multi-Issue Comparison

| Aspect | Single-issue structure | Multi-issue structure |
|---|---|---|
| Overall sentiment | `Customer_Sentiment` | `Overall_Customer_Sentiment` |
| Category | One `Main_Category` | One `Main_Category` per issue |
| Issue identity | No issue identifier documented | `Issue_ID` |
| Summary limit | Maximum 100 words | Maximum 75 words per issue |
| Resolution points | Added as `Actionable_Resolution_Points` in version `2.0.0` | Present for each issue |
| Priority | Not present in the initial structure | `Priority` with `High`, `Medium`, `Low` |
| Issue count | Single issue-oriented object | Top-level `Issues` array with one issue object per distinct issue |

Sources:

- Assessment PDF, Tasks 1, 2, and 4, printed pp. 3–9
- `PROMPT_DOCUMENTATION.md`, “Single-Issue to Multi-Issue Evolution”
- Screenshots 04–06

This comparison describes documented requirements and visible evidence. It does not imply that constraints from the initial structure automatically carry into the multi-issue structure.

## Known Schema and Validation Gaps

The following information is missing or only partially available:

- No machine-readable JSON Schema.
- The exact top-level `Issues` array structure is partial.
- No complete multi-issue JSON object is available.
- No additional-property rules are documented.
- No general nullability rules are documented.
- `N/A` is documented only for missing `Order_Reference_ID` and `Product_Reference`.
- No formal pattern validation is documented for IDs or order references.
- No deterministic priority-scoring formula is documented.
- No confidence-score field is documented.
- No automated validation implementation exists in the repository evidence.
- Screenshot output is not proof of automated JSON validation.
- No complete saved Assistant-role output is available.

No additional fields, data types, enum values, nullability rules, or validation constraints are inferred beyond the documented evidence.
