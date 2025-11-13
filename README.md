# English Tutor — Persistent AI Learning Repository

This repository acts as **external, persistent memory** for an AI-driven English learning system.  
It stores all **class sessions, evaluations, progress records, and reports**, allowing the AI tutor to continue the course seamlessly across days, conversations, or even different ChatGPT accounts.

The AI does **not** write to this repository directly.  
Instead, it generates JSON files as **plain text**, and the user manually commits them into this repository.

---

## Purpose

- Provide long-term, structured memory for an English course.
- Track progress from **B1+/intermediate** to **B2/C1 advanced**.
- Store all sessions, evaluations, reports, mistakes, and learning goals.
- Serve as the stable memory source used whenever the AI starts a session (e.g., via the phrase **"I am here for the English course"**).

---

## How It Works

1. User says: **"I am here for the English course."**
2. The AI reads:
   - `/manifests/INDEX.md`
   - `/instructions/assistant_instructions.md`
   - `/instructions/learning_plan.md`
   - `/data/progress.json`
3. The AI automatically scans:
   - the **most recent evaluation** from `/data/evaluations/`
   - the **most recent session** from `/data/sessions/`
4. The AI teaches the class or runs the evaluation.
5. The AI outputs new JSON files into **outbox paths** (as plain text).
6. The user commits them into:
   - `/data/sessions/`
   - `/data/evaluations/`
   - `/data/progress.json`

This creates a clean, version-controlled memory system for the entire course.

---

## Repository Structure

english-tutor/
│
├── README.md
│
├── instructions/
│ ├── assistant_instructions.md
│ ├── learning_plan.md
│ ├── initial_eval_guide.md
│ ├── evaluation_rubrics.md
│ └── validation_command.md
│
├── manifests/
│ └── INDEX.md
│
├── schemas/
│ ├── session.schema.json
│ ├── evaluation.initial.schema.json
│ ├── evaluation.biweekly.schema.json
│ ├── evaluation.bimonthly.schema.json
│ ├── progress.schema.json
│ ├── report.monthly.schema.json
│ ├── report.quarterly.schema.json
│ └── report.global.schema.json
│
├── data/
│ ├── progress.json
│ ├── stats.json
│ ├── sessions/
│ ├── evaluations/
│ └── summaries/
│
└── outbox/
├── sessions/
├── evaluations/
└── progress.json


---

## File Types

### **Class Sessions**
Stored in `/data/sessions/`  
Types:
- `study`
- `practice`
- `oral`
- `review`
- `thematic`

### **Evaluations**
Stored in `/data/evaluations/`  
Types:
- `initial`
- `biweekly`
- `bimonthly`

### **Reports**
Stored in `/data/summaries/`  
Types:
- monthly  
- quarterly  
- global  

### **Progress File**
`/data/progress.json`  
The **active memory state** of the course.

---

## Validation

All JSON files must comply with their corresponding schema inside `/schemas/`.

To validate via chat, the user can say:

> **"Validate this file for [type]"**

The AI will:
- load the correct schema  
- validate the structure  
- confirm validity or provide corrections  

---

## Workflow Summary

1. Start the session:  
   **“I am here for the English course.”**
2. AI loads context from the repository.
3. AI teaches class or runs evaluation.
4. AI generates JSON files.
5. User saves generated files in `/outbox/`.
6. User reviews and commits them into `/data/`.

---

## License

This repository contains personal learning progress.  
**No license provided. All rights reserved.**

---