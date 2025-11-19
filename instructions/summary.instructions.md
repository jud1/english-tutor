# Summary Instructions

## Purpose
Define the structure and required content for summary files generated after each class or session, based on `schemas/summary.schema.json`.

## Format
- File name: `outbox/summaries/YYYY-MM-DD-summary-NNN.json`
- Format: JSON

## Required Fields (see schema)
1. **meta**: Identity and scope of this summary file.
  - id: Unique identifier (e.g. summary-2025-11-15-001)
  - date: Date generated (YYYY-MM-DD)
  - type: Always 'summary'
  - generated_by: Tool or agent (e.g. 'copilot', 'human')
  - version: Schema/format version
2. **profile**: Static info about the learner and goals.
  - name: Learner name
  - goals: Main learning goals
3. **level_snapshot**: Current estimated level and skill scores.
  - cefr: Estimated CEFR level
  - skills: Scores per skill (listening, speaking, reading, writing)
  - confidence: Global confidence (0–100)
4. **timeline**: Period and elements covered.
  - period_start, period_end: Dates (update to reflect the range of classes/evaluations summarized)
  - related_sessions: IDs/filenames of session files (optional if not accessible, but include class context)
  - related_evaluations: IDs/filenames of evaluation files (optional if not accessible, but include results and observations)
5. **recent_work**: What was practiced recently.
  - topics: Main topics
  - activities: Types of activities
  - vocabulary: Words/phrases (term, meaning, example, notes)
  - homework: Previous/new tasks and results
6. **errors_and_risks**: Mistakes, blocks, risks.
  - active_mistakes: Patterns, status, examples
  - blocks: Psychological/practical blocks
  - risks: Risks for progress
7. **next_focus**: Focus for upcoming classes.
  - skills: Skills to prioritize
  - topics: Topics to address
  - recommendations: General suggestions
8. **notes**: Free-form notes for future sessions.
  - teacher_observations: Key insights
  - for_ai_tutor: Optional notes for AI tutor

## Example
```json
{
  "meta": {
    "id": "summary-2025-11-17-001",
    "date": "2025-11-17",
    "type": "summary",
    "generated_by": "copilot",
    "version": "1.0"
  },
  "profile": {
    "name": "Jose",
    "goals": ["Professional communication", "Technical English for software development", "Daily-living English for Japan"]
  },
  "level_snapshot": {
    "cefr": "B1+",
    "skills": {
      "listening": 75,
      "speaking": 70,
      "reading": 80,
      "writing": 65
    },
    "confidence": 72
  },
  "timeline": {
    "period_start": "2025-11-10",
    "period_end": "2025-11-17",
    "related_sessions": ["session-2025-11-10-001", "session-2025-11-12-002"],
    "related_evaluations": ["evaluation-2025-11-15-001"]
  },
  "recent_work": {
    "topics": ["IT interview questions", "present perfect"],
    "activities": ["study class", "oral practice"],
    "vocabulary": {
      "words": [
        {"term": "algorithm", "meaning": "step-by-step procedure", "example": "We used an algorithm to solve the problem.", "notes": "Common in IT"}
      ],
      "phrases": [
        {"expression": "on the fly", "meaning": "immediately, without preparation", "example": "He fixed the bug on the fly.", "notes": "Useful for interviews"}
      ]
    },
    "homework": {
      "previous_assigned": ["Write a technical email"],
      "previous_result": "Completed with minor errors.",
      "new_assigned": ["Prepare answers for common interview questions"]
    }
  },
  "errors_and_risks": {
    "active_mistakes": [
      {
        "label": "present perfect vs past simple",
        "description": "Confuses the two tenses.",
        "examples": [
          {"wrong": "I have went", "correct": "I have gone"}
        ],
        "status": "persistent"
      }
    ],
    "blocks": ["fear of speaking"],
    "risks": ["irregular schedule"]
  },
  "next_focus": {
    "skills": ["speaking fluency"],
    "topics": ["past tenses"],
    "recommendations": ["Increase oral practice"]
  },
  "notes": {
    "teacher_observations": "Jose is progressing well but needs more confidence in speaking.",
    "for_ai_tutor": "Focus on error correction and encourage participation."
  }
}
```

## Notes and Recommendations
- Always follow the schema for field names and structure.
- The summary should be as complete as possible, integrating all relevant information from recent classes and weekly evaluations, even if you cannot list specific files.
- If you do not have access to session or evaluation files, summarize topics, errors, and results in the corresponding fields.
- Update `period_start` and `period_end` to reflect the range covered by the summary.
- The summary acts as extended memory for GPT: it must contain context, progress, errors, observations, and recent results.
- Keep summaries focused and clear, but detailed enough to provide a complete picture of progress and challenges.
