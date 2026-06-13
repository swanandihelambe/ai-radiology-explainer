# Database Schema

## Overview

The MVP uses a single database table to store generated analysis results.

The design is intentionally simple and can be expanded in future versions.

---

## Table: analysis_history

| Column Name | Data Type          | Description                  |
| ----------- | ------------------ | ---------------------------- |
| id          | SERIAL PRIMARY KEY | Unique analysis identifier   |
| created_at  | TIMESTAMP          | Analysis creation timestamp  |
| report_type | TEXT               | Chest X-Ray or Bone X-Ray    |
| findings    | JSON               | Extracted findings           |
| explanation | TEXT               | Patient-friendly explanation |
| glossary    | JSON               | Medical glossary terms       |
| questions   | JSON               | Doctor discussion questions  |

---

## Example Record

```json
{
  "id": 1,
  "created_at": "2026-06-13 20:30:00",
  "report_type": "Chest X-Ray",
  "findings": [
    "Pleural Effusion (Small)"
  ],
  "explanation": "A small amount of fluid is present around the left lung.",
  "glossary": [
    {
      "term": "Pleural Effusion",
      "definition": "Fluid buildup around the lungs."
    }
  ],
  "questions": [
    "What might cause this finding?",
    "Should this finding be monitored?"
  ]
}
```

---

## MVP Design Decisions

* Single-table design
* No patient-identifiable information
* No raw report storage
* No raw image storage
* JSON used for structured output fields

---

## Future Schema Expansion

Future versions may add:

* User Accounts
* Secure Report Storage
* Secure Image Storage
* Audit Logs
* Access Control
* Consent Tracking
* Multi-Study Support

