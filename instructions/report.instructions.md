# Report Generation Instructions

## Purpose
These instructions guide the assistant to automatically generate periodic reports (monthly, quarterly, etc.) using the data stored in the `data/` folder. Reports provide a global, synthesized view of progress, trends, and achievements, based on evaluations, sessions, summaries, and progress files.

## Data Sources
- `data/evaluations/`: Contains individual evaluation results.
- `data/sessions/`: Contains session records and feedback.
- `data/summaries/`: Contains summary files for each class or period.
- `data/progress.json`: Tracks overall progress metrics.

## Report Frequency
- Recommended: Monthly or quarterly (can be adjusted as needed).
- Periodic reports (monthly, quarterly) can be generated at any time, even if the course has already started. They are not mandatory for every period unless explicitly needed.
- Only the global report (`report.global.schema.json`) should be updated over time to reflect the overall progress and accumulated results. Periodic reports are snapshots and do not require updates after creation.

## Report Format
- Use the corresponding schema in `schemas/` (e.g., `report.monthly.schema.json`, `report.quarterly.schema.json`, `report.global.schema.json`).
- The report must be a valid JSON file matching the schema.

## Generation Steps
1. Collect all relevant data files from the period (evaluations, sessions, summaries, progress).
2. Synthesize key metrics, trends, and notable achievements.
3. Summarize strengths, areas for improvement, and recommendations.
4. Structure the report according to the chosen schema.
5. Save the report in the appropriate folder (e.g., `data/reports/`).

## Example Workflow
- At the end of each month, gather all evaluations and summaries from the last 30 days.
- Calculate average scores, progress, and highlight improvements.
- Write a summary of strengths and areas to focus on next month.
- Generate a JSON report using `report.monthly.schema.json`.

## Notes
- Reports should not duplicate information; they must synthesize and contextualize.
- If any required data is missing, note it in the report and proceed with available information.
- Always validate the report against its schema before saving.
- Only the global report is meant to be updated as the course progresses. Periodic reports are generated as needed and remain static once created.

## References
- [report.monthly.schema.json](../schemas/report.monthly.schema.json)
- [report.quarterly.schema.json](../schemas/report.quarterly.schema.json)
- [report.global.schema.json](../schemas/report.global.schema.json)

---

For questions or custom report requests, refer to this file or contact the repository maintainer.