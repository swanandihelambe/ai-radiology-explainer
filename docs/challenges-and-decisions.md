# Challenges and Decisions

## Challenge 1: X-Ray Image and Report Pair Availability

### Problem

Finding publicly available datasets containing both X-Ray images and corresponding radiology reports proved difficult.

### Decision

Version 1 focuses primarily on radiology report interpretation while allowing optional X-Ray image uploads.

### Future Improvement

Investigate datasets containing paired image-report studies for image-to-report contextual analysis.

---

## Challenge 2: Report Classification Strategy

### Problem

The system must distinguish Chest X-Ray reports, Bone X-Ray reports, and unsupported report types.

### Options Considered

1. Rule-Based Classification
2. AI-Based Classification using Gemini

### Decision

Rule-based classification was selected for the MVP because it is faster, cheaper, and does not consume AI API requests.

### Future Improvement

Replace rule-based classification with AI-powered classification for improved scalability and flexibility.

---

## Challenge 3: Medical Terminology Complexity

### Problem

Radiology reports contain terminology that may be difficult for non-medical users to understand.

### Decision

Implemented patient-friendly explanations and glossary generation using Google Gemini.

### Outcome

Patients can understand report findings without needing advanced medical knowledge.

---

## Challenge 4: Findings vs Educational Terms

### Problem

Reports often mention conditions that are explicitly absent.

Example:

* No pneumothorax
* No pleural effusion

Displaying these terms as findings could confuse users.

### Decision

Separate output into:

* Important Findings in Your Report
* Other Medical Terms Mentioned

### Outcome

Users can learn medical terminology without assuming those conditions are present.

---

## Challenge 5: AI Output Consistency

### Problem

Generative AI responses can vary in structure and formatting.

### Decision

Introduced strict prompt formatting rules and output templates.

### Outcome

More consistent and predictable results.

---

## Challenge 6: API Usage and Cost

### Problem

Using AI for every task increases API usage and may introduce quota limitations.

### Decision

Use AI only where it provides significant value:

* Patient-Friendly Explanation
* Medical Glossary Generation
* Doctor Discussion Questions

Use traditional programming for:

* PDF Processing
* Report Validation
* Report Classification

### Outcome

Reduced API usage and improved performance.

---

## Known Limitations

* Version 1 does not perform independent diagnosis.
* Version 1 does not recommend treatments.
* Version 1 does not directly analyze X-Ray images.
* Version 1 currently supports only Chest and Bone X-Ray reports.
* Report classification relies on predefined rules.
* Output quality depends on the quality of the uploaded report.
