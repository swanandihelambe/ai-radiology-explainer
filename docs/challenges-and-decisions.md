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

Radiology reports often mention important medical conditions even when they are explicitly absent from the patient's study.
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

## Challenge 7: False Positive Finding Detection

### Problem

Initial finding extraction relied on simple keyword matching.

This caused findings to be detected even when they were explicitly stated as absent.

Examples:

* No pneumothorax
* No pleural effusion

### Decision

Implemented basic negation handling by examining text immediately preceding supported finding keywords.

### Outcome

Reduced false-positive findings and improved extraction accuracy for supported Chest and Bone X-Ray reports.

---

## Challenge 8: Non-Radiology Report Processing

### Problem

Keywords such as "pneumonia" appeared inside laboratory and respiratory panel reports.

This caused unsupported reports to incorrectly trigger finding detection.

### Example

A respiratory panel report mentioned pneumonia in educational text even though it was not an imaging finding.

### Decision

Restricted finding extraction to supported radiology report categories only.

### Outcome

Prevented false findings from unrelated medical report types.

---

## Challenge 9: Keyword Detection vs True Finding Extraction

### Problem

Simple keyword matching does not fully understand report context.

A medical term may be:

* Present
* Absent
* Historical
* Mentioned for educational purposes

### Decision

Use rule-based keyword extraction with basic negation handling for the MVP.

### Future Improvement

Investigate NLP-based finding extraction and contextual understanding for improved accuracy.

### Outcome

Delivered a lightweight and explainable extraction system suitable for the MVP.

---

## Challenge 10: Public Dataset Quality and Availability

### Problem

Many publicly available medical datasets either:

* Contain images without reports
* Contain reports without images
* Have incomplete metadata
* Require additional preprocessing before use

This made realistic end-to-end testing difficult during MVP development.

### Decision

Use a combination of publicly available reports, sample reports, and controlled test cases during development.

### Future Improvement

Build a larger curated testing dataset containing both X-Ray images and corresponding radiology reports.

### Outcome

Enabled MVP validation despite limited availability of paired image-report datasets.

---
## Challenge 10: PDF Text Normalization

### Problem

Some radiology PDFs contained Unicode and font-encoding artifacts during text extraction.

Example:

* Pleural eưusion

instead of

* Pleural Effusion

This caused valid findings to be missed during keyword matching.

### Decision

Implemented a text normalization layer before report classification and finding extraction.

### Outcome

Improved finding extraction reliability across real-world radiology PDFs.

---
## Known Limitations

* Version 1 does not perform independent diagnosis.
* Version 1 does not recommend treatments.
* Version 1 does not directly analyze X-Ray images.
* Version 1 currently supports only Chest and Bone X-Ray reports.
* Report classification relies on predefined rules.
* Output quality depends on the quality of the uploaded report.
