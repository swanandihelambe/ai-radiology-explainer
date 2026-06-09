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

### Current MVP Features

* PDF Upload
* Text Extraction
* Report Classification
* AI Explanation Generation
* Optional Image Upload

### Future Work

* Medical glossary generation
* Doctor discussion questions
* Analysis history
* Image-to-report contextual analysis
* AI-based report classification
* CT/MRI/Ultrasound support

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

### Current MVP Features

* PDF Upload
* Optional X-Ray Image Upload
* PDF Text Extraction
* Report Classification
* Patient-Friendly Explanation
* Medical Glossary Generation
* Doctor Discussion Questions

### Future Work

* Medical Finding Extraction
* Analysis History Tracking
* Image-to-Report Contextual Analysis
* AI-Based Report Classification
* CT Report Support
* MRI Report Support
* Ultrasound Report Support
* Multilingual Support

### Notes

* Public datasets containing both X-Ray images and corresponding radiology reports are difficult to obtain.
* The current MVP primarily focuses on report interpretation while allowing optional image uploads.
* Prompt engineering significantly improved output quality and consistency.
