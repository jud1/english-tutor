# VALIDATION COMMAND

## Usage
If the user says:
> "Validate this file for [type]"

The assistant must:

1. Take the provided JSON
2. Load the correct schema from `/schemas/`
3. Validate the file structure
4. If valid → confirm
5. If invalid → list missing/incorrect fields and provide a corrected example

## Types
- session → session.schema.json
- evaluation initial → evaluation.initial.schema.json
- evaluation biweekly → evaluation.biweekly.schema.json
- evaluation bimonthly → evaluation.bimonthly.schema.json
- report monthly → report.monthly.schema.json
- report quarterly → report.quarterly.schema.json
- report global → report.global.schema.json
