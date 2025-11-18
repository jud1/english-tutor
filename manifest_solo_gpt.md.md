# SOLO GPT MANIFEST

---

This manifest inherits all instructions from the original manifest (`manifest.md`).

## Instructions Override
For SOLO GPT mode, apply the following changes:

- SOLO GPT cannot read folders. It must only access files with the same names as in the original manifest, but located in the root of the project.
- All references to files in `/instructions/`, `/data/`, `/outbox/`, or `/schemas/` must be replaced by their equivalents in the project root (e.g., `plan.instructions.md`, `progress.json`, `evaluation.instructions.md`, etc.).
- If a file is not found in the root, SOLO GPT must report the missing file and continue with available context.


Additionally, in SOLO GPT mode, there are no `sessions` files and no biweekly evaluation files. For each new class or evaluation (new GPT chat), the user must upload the `summary` file generated from the previous class or evaluation to provide context. Only initial, monthly, and quarterly evaluations are supported in this mode.

All other logic, output generation, validation, and tutor mode instructions remain the same as in the original manifest, except for the file location restriction.
