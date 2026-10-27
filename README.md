# SAP Generative AI Feedback Analyzer

## Overview
This repository documents work completed in SAP AI Launchpad Prompt Editor using the `feedback-analyzer-CERT1834` prompt template in the `orchestration` scenario.

The project focuses on analyzing customer feedback emails and returning structured JSON for routing, including issue category, customer sentiment, issue summary, order/product references, suggested department, actionable resolution points, and multi-issue prioritization.

## Official task instructions
The original SAP assessment task-instructions PDF is included here:
[`02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf`](02_Project/SAP-Generative-AI-Developer-Assessment-Task-Instructions.pdf)

It describes the assessment tasks and expected deliverables. It is the task brief, not an export of the completed prompt template.

## Model comparison
The supplied screenshots show three models tested on a delivery-problem example:

- **Gemini 2.5 Flash Lite (001):** appears to be the strongest fit among the shown examples because its response includes the expected structured routing fields.
- **GPT-4.1 nano:** returned a compact structured response.
- **GPT-5-Mini:** returned a structured response with a more descriptive issue summary.

This is a qualitative observation from the screenshots, not a formal benchmark or a claim that one model is universally best.

## Screenshots
- [`01-Gemini-2.5-Flash-Lite-Response.png`](03_Screenshots/01-Gemini-2.5-Flash-Lite-Response.png)
- [`02-GPT-4.1-nano-Response.png`](03_Screenshots/02-GPT-4.1-nano-Response.png)
- [`03-GPT-5-Mini-Response.png`](03_Screenshots/03-GPT-5-Mini-Response.png)
- [`04-Structured-JSON-Schema-and-Issue-Extraction.png`](03_Screenshots/04-Structured-JSON-Schema-and-Issue-Extraction.png)
- [`05-Multi-Issue-Extraction-Prompt.png`](03_Screenshots/05-Multi-Issue-Extraction-Prompt.png)
- [`06-Actionable-Resolution-Points-Output.png`](03_Screenshots/06-Actionable-Resolution-Points-Output.png)

## Certification
**SAP Certified - SAP Generative AI Developer**

[View public Credly badge](https://www.credly.com/badges/8a5f8129-4b14-4918-8d71-1a2550539478/public_url)

## Repository structure
- `01_Certificate/` — certification PDF.
- `02_Project/` — original SAP assessment task-instructions PDF.
- `03_Screenshots/` — six screenshots supplied for this project.
- `README.md` — the only README in this repository.

## Note
The task-instructions PDF explains the assessment requirements; it is not a deployable SAP prompt-template export. No SAP credentials or private account information are included.
