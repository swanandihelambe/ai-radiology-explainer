# Development Log

## June 1, 2026

### Completed

* Researched Chest X-Ray findings:

  * Cardiomegaly
  * Pleural Effusion

* Researched Bone X-Ray findings:

  * Fracture
  * Osteoarthritis

* Updated domain research documentation.

### Notes

* Findings should be explained as observations, not diagnoses.
* Patient-friendly explanations must remain educational and neutral.

---

## June 3–6, 2026

### Completed

* Researched:

  * Pneumonia
  * Pneumothorax
  * Dislocation
  * Joint Space Narrowing

* Expanded domain research documentation.

* Created sample report collection strategy.

### Notes

* Real-world radiology reports vary significantly in structure and terminology.

---

## June 8, 2026

### Completed

* Set up Streamlit application.
* Created project virtual environment.
* Configured project dependencies.
* Implemented PDF report upload.
* Implemented PDF text extraction using PyMuPDF.
* Implemented optional X-Ray image upload and preview.
* Integrated Google Gemini API.
* Implemented AI-generated patient-friendly explanations.
* Implemented report type classification.
* Added validation for unsupported report types.

### Key Decisions

* Radiology Report PDF is required for Version 1.
* X-Ray image upload is optional.
* Rule-based classification is used for the MVP.
* AI-based classification may be added in a future version.

---

## June 9, 2026

### Completed

* Implemented Medical Glossary Generation.

* Implemented Doctor Discussion Questions.

* Improved patient-friendly explanation prompts.

* Added separation between:

  * Important Findings in Your Report
  * Other Medical Terms Mentioned

* Improved output formatting using Markdown structure.

* Tested the application using sample Chest X-Ray reports.

### Key Decisions

* Educational medical terms should be separated from actual findings.
* Patients should be able to learn terminology even when findings are absent from their study.
* Doctor discussion questions should focus on understanding findings rather than treatment recommendations.
* Medical terminology should be simplified while preserving the original report meaning.


### Notes

* Public datasets containing both X-Ray images and corresponding radiology reports are difficult to obtain.
* The current MVP primarily focuses on report interpretation while allowing optional image uploads.
* Prompt engineering significantly improved output quality and consistency.

---

## June 10, 2026

### Completed

* Implemented Medical Finding Extraction V1.
* Added support for detecting:
  * Cardiomegaly
  * Pleural Effusion
  * Pneumonia
  * Pneumothorax
  * Fracture
  * Osteoarthritis
  * Dislocation
  * Joint Space Narrowing
* Added a Detected Findings section to the user interface.
* Restricted finding extraction to supported Chest and Bone X-Ray reports.
* Implemented basic negation handling for absent findings.
* Tested finding extraction using Chest X-Ray and non-radiology reports.

### Key Decisions

* Finding extraction uses rule-based keyword matching for the MVP.
* Finding extraction is performed only for supported radiology reports.
* Basic negation handling was introduced to reduce false-positive findings.
* Non-radiology reports are excluded from finding extraction.

### Notes

* Simple keyword matching can produce false-positive findings.
* Basic negation handling improved extraction accuracy for phrases such as:
  * No pneumothorax
  * No pleural effusion
* Future versions may use NLP-based extraction and severity detection.
* Testing with non-radiology reports helped identify edge cases and improve extraction reliability.

---

## June 11, 2026

### Completed

* Implemented Finding Severity Detection V1.

* Added support for severity indicators:

  * Minimal
  * Small
  * Mild
  * Moderate
  * Large
  * Severe
  * Displaced
  * Non-Displaced

* Enhanced finding extraction to display severity information when available.

* Implemented PDF text normalization for malformed medical terms caused by PDF extraction artifacts.

* Fixed Pleural Effusion detection issues caused by Unicode and font-encoding inconsistencies.

* Tested finding extraction and severity detection using real-world Chest X-Ray reports.

### Key Decisions

* Severity detection remains rule-based for the MVP.
* PDF text normalization is performed before report classification and finding extraction.
* Findings should include severity information whenever explicitly mentioned in the report.
* Text preprocessing is required to improve reliability when working with real-world radiology PDFs.

### Notes

* Real-world PDF extraction may introduce Unicode and font-encoding artifacts.
* Text normalization significantly improved finding extraction accuracy.
* Severity detection improved the clinical usefulness of extracted findings without requiring additional AI API calls.
* Additional report variations and edge cases will continue to be tested as the dataset grows.

---


## June 13, 2026

### Completed

* Designed Analysis History feature.
* Defined MVP privacy strategy.
* Designed database schema for analysis storage.
* Created AnalysisHistoryDesign.md.
* Created DatabaseSchema.md.

### Key Decisions

* Generated analysis results will be stored.
* Patient-identifiable information will not be stored.
* Raw reports and X-Ray images will not be stored in the MVP.
* JSON will be used for structured output fields.

### Notes

* Privacy considerations were incorporated into the MVP design.
* Database design was finalized before PostgreSQL implementation.
