# MediAssist AI — Healthcare Assistant using Hugging Face & Prompt Engineering

## Overview

MediAssist AI is a prototype healthcare chatbot built for **MediAssist AI Pvt. Ltd.**, designed to help doctors summarize patient reports, answer clinical questions, and generate discharge summaries. The original chatbot suffered from inconsistent responses, hallucinated medical information, unstructured outputs, and prompts that were hard to maintain.

This project rebuilds the assistant using **Hugging Face Transformers** for model inference and **structured Prompt Engineering techniques** (role prompting, few-shot examples, chain-of-thought reasoning, and constrained output formatting) to produce reliable, consistent, and well-formatted clinical responses. It also demonstrates model-agnostic design — the same prompt templates work across different Hugging Face models, so the underlying LLM can be swapped without rewriting application logic.

## Features

- Interactive chatbot for clinical Q&A using an instruction-tuned Hugging Face model
- Role-based, context-aware prompting to reduce hallucinations and improve response consistency
- Few-shot prompting to convert raw clinical notes into structured summaries
- Chain-of-thought reasoning for symptom-based triage recommendations (internal reasoning hidden from final output)
- Structured JSON output mode for downstream system integration
- Side-by-side comparison of two Hugging Face models on identical prompts
- Role-adaptive response templates (Doctor / Nurse / Medical Student / Patient) using a single underlying model

## Project Structure

    MediAssist-AI/
    │
    ├── MediAssist_AI.ipynb # Main Colab notebook (all tasks)
    ├── README.md # Project documentation
    ├── report/
    │ └── MediAssist_AI_Report.pdf # 2–3 page report (model selection, techniques, challenges)
    ├── screenshots/
    │ ├── task1_chatbot_interaction.png
    │ ├── task2_prompt_engineering.png
    │ ├── task3_fewshot_output.png
    │ ├── task4_cot_output.png
    │ ├── task5_json_output.png
    │ ├── task6_model_comparison.png
    │ └── bonus_role_based_output.png
    └── requirements.txt # Dependency list

## Tech Stack

- **Language:** Python 3
- **Environment:** Google Colab (GPU runtime — T4)
- **Core Library:** Hugging Face Transformers
- **Supporting Libraries:** PyTorch, Accelerate, SentencePiece
- **Techniques:** Prompt Engineering (Role Prompting, Few-Shot Prompting, Chain-of-Thought Prompting, Structured Output Prompting)

## Hugging Face Models Used

| Model                              | Parameters | Purpose                                                                    |
| ---------------------------------- | ---------- | -------------------------------------------------------------------------- |
| `microsoft/Phi-3-mini-4k-instruct` | 3.8B       | Primary chatbot model — detailed, instruction-following clinical responses |
| `Qwen/Qwen2.5-1.5B-Instruct`       | 1.5B       | Secondary model for comparison (Task 6) — lightweight, faster inference    |

> Fallback option if either model is gated or slow to download on Colab: `TinyLlama/TinyLlama-1.1B-Chat-v1.0`

## How to Run

1. Open `MediAssist_AI.ipynb` in **Google Colab**
2. Go to **Runtime → Change runtime type → GPU (T4)**
3. Run cells in order:
   - Cell 1–2: install dependencies and load the primary model
   - Cell 3–4: Task 1 — interactive chatbot
   - Cell 5: Task 2 — structured prompt engineering
   - Cell 6: Task 3 — few-shot clinical note summarizer
   - Cell 7: Task 4 — chain-of-thought triage prompt
   - Cell 8: Task 5 — structured JSON output
   - Cell 9: Task 6 — load second model and compare
   - Cell 10: Task 7 — optimized/hallucination-reduced prompt
   - Cell 11: Bonus — role-based prompt template
4. For the interactive chatbot (Task 1), type a query when prompted and type `exit` to stop
5. Take screenshots of key outputs for the deliverables folder
6. Download the notebook via **File → Download → .ipynb** for submission

## Author

**Shivansh Kumar**
Roll No. 2301921520178
G L Bajaj Institute of Technology and Management
