# Model Comparison

## 1. Purpose and Scope

This document records the model-comparison evidence available in this repository for the SAP Generative AI customer-feedback analysis project.

The comparison is limited to the visible Prompt Editor configuration and response screenshots. It documents observable response presentation and field visibility only. It does not provide benchmark scores, accuracy measurements, latency, cost, token usage, repeated-run consistency, or a definitive model ranking.

The assessment instructions require a model comparison and selection. The repository evidence is insufficient to independently verify a winning model or reproduce a complete evaluation dataset.

Evidence sources include:

- `README.md`
- `PROMPT_DOCUMENTATION.md`
- `OUTPUT_SCHEMA.md`
- `SAMPLE_TEST_CASES.md`
- `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`
- `03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png`
- `03_Screenshots/02-GPT-4.1-nano-Response.png`
- `03_Screenshots/03-GPT-5-Mini-Response.png`

## 2. Models Evaluated

The three model identifiers visible in the comparison screenshots are:

| Model | Exact visible identifier | Screenshot |
|---|---|---|
| Gemini | `Gemini 2.5 Flash Lite (001)` | `03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png` |
| GPT-4.1 | `GPT-4.1 nano (2025-04-14)` | `03_Screenshots/02-GPT-4.1-nano-Response.png` |
| GPT-5 | `GPT-5-Mini (2025-08-07)` | `03_Screenshots/03-GPT-5-Mini-Response.png` |

The screenshots show the following visible parameter counts:

| Model | Visible parameter count |
|---|---:|
| `Gemini 2.5 Flash Lite (001)` | `Parameters (3)` |
| `GPT-4.1 nano (2025-04-14)` | `Parameters (5)` |
| `GPT-5-Mini (2025-08-07)` | `Parameters (2)` |

Only the counts are visible. Parameter names and values are not available in the repository evidence.

## 3. SAP AI Launchpad Prompt Editor Setup

The documented comparison uses:

| Configuration item | Evidence-supported value |
|---|---|
| Platform | SAP AI Launchpad Prompt Editor |
| Template | `feedback-analyzer-CERT1834` |
| Scenario | `orchestration` |
| Prompt version | `2.0.0` |
| Comparison input | Delivery feedback concerning order `#GGX33445` and `Premium Coffee Maker` |

The three comparison screenshots visibly show the same template context, scenario, prompt version, and general delivery-feedback scenario.

The screenshots visibly show these seven base response fields:

- `Feedback_ID`
- `Main_Category`
- `Customer_Sentiment`
- `Issue_Summary`
- `Order_Reference_ID`
- `Product_Reference`
- `Suggested_Department`

`OUTPUT_SCHEMA.md` documents `Actionable_Resolution_Points` for prompt version `2.0.0`. However, screenshots 01–03 do not visibly confirm that field. Therefore, the screenshots do not establish the complete version `2.0.0` schema.

The repository does not contain a complete exported Prompt Editor configuration, complete parameter settings, or a machine-readable response schema.

## 4. Comparison Methodology

### Assessment-defined methodology

The assessment requires the evaluator to:

1. Use prompt version `2.0.0`.
2. Process the delivery feedback concerning order `#GGX33445`.
3. Run the same task with different available LLMs.
4. Review the generated JSON for accuracy, completeness, and format adherence.
5. Compare the outputs.
6. Select the best-performing model for the current setup.
7. Save the selected output as `Optimal Model Output` in version `2.2.0`.

Source: `02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`, Task 3.1, printed p. 7.

### Repository-confirmed execution evidence

Screenshots 01–03 show one visible response panel for each of the three models. They provide qualitative evidence that structured JSON-shaped responses were displayed for the delivery-comparison scenario.

The repository does not provide:

- A complete record of repeated executions.
- Formal evaluation scores.
- A documented accuracy or completeness review.
- The final model-selection rationale.
- The saved `Optimal Model Output`.

## 5. Available Response Evidence

### Gemini 2.5 Flash Lite

Source: `03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png`.

The screenshot visibly shows a structured response associated with the delivery scenario. The visible response includes the seven base fields listed in Section 3. The displayed issue summary is partially clipped horizontally in the screenshot.

### GPT-4.1 nano

Source: `03_Screenshots/02-GPT-4.1-nano-Response.png`.

The screenshot visibly shows a structured response associated with the same delivery scenario. The visible response includes the seven base fields listed in Section 3 and is presented in a compact response view.

### GPT-5-Mini

Source: `03_Screenshots/03-GPT-5-Mini-Response.png`.

The screenshot visibly shows a structured response associated with the same delivery scenario. The visible response includes the seven base fields listed in Section 3 and displays a more descriptive issue-summary presentation.

These descriptions refer to visible presentation and field text only. They are not claims about response accuracy or model quality. The screenshots show JSON-shaped text but do not prove automated JSON parsing or validation.

## 6. Observable Differences

The following differences are limited to what can be seen in the comparison screenshots:

| Observation | `Gemini 2.5 Flash Lite (001)` | `GPT-4.1 nano (2025-04-14)` | `GPT-5-Mini (2025-08-07)` |
|---|---|---|---|
| Structured JSON-shaped response displayed | Yes | Yes | Yes |
| Seven base fields visibly present | Yes | Yes | Yes |
| Response presentation | Structured response view; issue summary partly clipped | Compact structured response view | Structured response view with a more descriptive visible issue summary |
| Visible parameter count | `Parameters (3)` | `Parameters (5)` | `Parameters (2)` |
| Parameter names and values visible | No | No | No |

The table records visual observations only. It does not establish accuracy, completeness, consistency, latency, cost, or ranking.

The screenshots do not visibly confirm `Actionable_Resolution_Points`, even though that field is documented in `OUTPUT_SCHEMA.md` as part of the prompt version `2.0.0` extension.

## 7. Evidence Limitations

The available evidence does not establish:

- Benchmark scores or accuracy percentages.
- Formal completeness or format-adherence scores.
- Latency or throughput.
- Token usage or cost.
- Repeated-run consistency.
- Parameter names or parameter values.
- A complete exported prompt configuration.
- A complete copy of each generated response.
- Automated JSON parsing or validation.
- The full input text as displayed during every model run.
- The selected model or the rationale for selecting it.
- The saved `Optimal Model Output` in prompt version `2.2.0`.

Some screenshot content is clipped or constrained by the visible Prompt Editor area. Incomplete screenshot text is not reproduced as a complete response fixture.

The assessment requires selecting the best-performing model and saving its output as `Optimal Model Output` in version `2.2.0`. The repository does not contain sufficient evidence to identify which model was selected or to verify that the required saved output exists.

## 8. Conclusion

The repository provides visual evidence that `Gemini 2.5 Flash Lite (001)`, `GPT-4.1 nano (2025-04-14)`, and `GPT-5-Mini (2025-08-07)` were evaluated in the SAP AI Launchpad Prompt Editor using the `feedback-analyzer-CERT1834` template, the `orchestration` scenario, and prompt version `2.0.0`.

All three comparison screenshots show JSON-shaped responses for the documented delivery scenario and visibly include the same seven base fields. The screenshots show differences in response presentation, including a partially clipped Gemini summary, a compact GPT-4.1 nano response view, and a more descriptive visible GPT-5-Mini issue summary.

These observations are not sufficient to declare a winning model. The repository does not contain the measurements, repeated-run evidence, selection rationale, or verified `Optimal Model Output` required to support that conclusion.
