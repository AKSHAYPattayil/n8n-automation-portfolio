# AI Prompt Generator – n8n Workflow

This workflow generates **high-quality, copy-paste-ready AI prompts** by progressively refining vague user intent into a structured, deterministic prompt.

It is designed to reduce ambiguity when building AI agents, tools, or automations.

---

## Problem

Users often know *what* they want to build with AI, but struggle to:
- Clearly define inputs and outputs
- Anticipate missing context
- Write prompts that are structured and reusable

This leads to poor LLM results and repeated prompt iteration.

---

## Solution

This n8n automation uses a **multi-step, AI-assisted refinement flow**:

1. Collects the user’s initial intent via a form
2. Uses an LLM to generate **clarifying questions**
3. Dynamically renders a second form based on those questions
4. Merges all responses into a final, structured prompt
5. Outputs a **clean, copy-paste-ready prompt** for downstream AI agents

---

## Workflow Overview

**High-level flow:**

- Form Trigger → Base Questions
- LLM-generated clarification questions
- Dynamic form rendering
- Split / Loop / Merge aggregation
- Final prompt synthesis with strict formatting
- Auto-fixing parser for output reliability

This design prioritizes **clarity, reliability, and UX**.

---

## Key Features

- Dynamic form generation using LLM structured output
- JSON schema-driven question formatting
- Auto-healing output parser to handle malformed responses
- Modular node design for easy extension
- No hard-coded credentials or secrets
- Model-agnostic design: the LLM can be swapped (Gemini, OpenAI, etc.) without changing the workflow logic

---

## Tech Stack

- n8n
- Google Gemini
- Structured Output Parsers
- Auto-fixing Output Parser
- Custom CSS for form UX

---

## Security Notes

- No API keys or secrets are hard-coded
- Credentials are managed via n8n’s credential system and are **not included** in the exported workflow
- Users must configure their own credentials after importing

---

## How to Use

1. Import `workflow.json` into n8n
2. Configure Google Gemini credentials
3. Run the workflow via the Form Trigger
4. Fill in the initial intent
5. Answer the generated clarifying questions
6. Copy the final generated prompt

---

## Possible Improvements

- Versioned prompt templates
- Prompt quality scoring
- Multi-language prompt support
- Export prompt as Markdown or JSON

---

## Inspiration & Attribution

This workflow is based on the **AI Prompt Generator** template published on the official n8n templates library by **Anurag Srivastava**.

The goal of this implementation was to deeply understand the design patterns used in the template and recreate the workflow end-to-end.

During replication, the workflow was:
- Rebuilt node-by-node rather than imported directly
- Studied for control flow, prompt structure, and parsing logic
- Extended and modified to improve clarity, modularity, and documentation
- Structured to be model-agnostic, allowing different LLM providers to be swapped in

This repository is intended as a **learning-focused reconstruction and extension**, not a verbatim copy.
