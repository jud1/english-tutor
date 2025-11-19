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



## Suggested Workflow

1. Start the session: "I am here for the English course."
2. The assistant loads the context from the repository (`/data/` files and relevant instructions).
3. The assistant teaches the class or runs the evaluation.
4. The assistant generates JSON files.
5. The user saves the generated files in `/outbox/`.
6. The user reviews and moves them to `/data/`.

This creates a clean, version-controlled memory system for the entire course.

---

## Repository Structure

english-tutor/
│


# English Tutor — Persistent AI Memory Repository

This repository stores the structured memory for an AI-powered English tutoring system. It contains sessions, evaluations, reports, and student progress, enabling continuity and traceability in learning.

---

## Purpose

- Provide persistent, structured memory for the English course.
- Track progress from intermediate to advanced levels.
- Store sessions, evaluations, reports, and learning goals.

---

## Current Repository Structure

```
english-tutor/
│
├── README.md
├── LICENSE
├── gpt_solo_instructions.md
├── manifest.md
├── manifest_solo_gpt.md.md
│
├── data/
│   ├── progress.json
│   ├── stats.json
│   ├── evaluations/        # (empty)
│   ├── sessions/           # (empty)
│   └── summaries/          # (empty)
│
├── instructions/
│   ├── class.instructions.md
│   ├── evaluation.instructions.md
│   ├── plan.instructions.md
│   ├── report.instructions.md
│   ├── summary.instructions.md
│   └── validation.instructions.md
│
├── manifests/              # (empty)
│
├── outbox/
│   ├── progress.json
│   ├── evaluations/        # (empty)
│   └── sessions/           # (empty)
│
├── schemas/
│   ├── evaluation.biweekly.schema.json
│   ├── evaluation.initial.schema.json
│   ├── evaluation.monthly.schema.json
│   ├── evaluation.quarterly.schema.json
│   ├── progress.schema.json
│   ├── report.global.schema.json
│   ├── report.monthly.schema.json
│   ├── report.quarterly.schema.json
│   ├── session.schema.json
│   └── summary.schema.json
```

**Note:** Several folders are empty and some files mentioned in previous README versions do not exist. The structure above is accurate.

---

## File Types

- **Class sessions:** `/data/sessions/` (currently empty)
- **Evaluations:** `/data/evaluations/` (currently empty)
- **Reports:** `/data/summaries/` (currently empty)
- **Progress:** `/data/progress.json` and `/outbox/progress.json`
- **JSON Schemas:** `/schemas/` (for file validation)

---

## Validation

All JSON files must comply with their corresponding schema in `/schemas/`.
To validate, you can ask the assistant:

> "Validate this file for [type]"

The assistant will load the schema, validate the structure, and suggest corrections if needed.

---

## Suggested Workflow

1. Start the session: "I am here for the English course."
2. The assistant loads the context from the repository.
3. The assistant teaches the class or runs the evaluation.
4. The assistant generates JSON files.
5. The user saves the generated files in `/outbox/`.
6. The user reviews and moves them to `/data/`.

---

## Repository Management Recommendations

- Keep the structure updated and remove references to non-existent files.
- Document any relevant changes in the README.
- Keep folders empty only if necessary; otherwise, remove unused folders.
- Use schemas to validate all files before adding them.
- If you add new types of sessions, evaluations, or reports, update the README and schemas accordingly.

---

## License

This repository contains personal learning progress.
**No explicit license. All rights reserved.**

---