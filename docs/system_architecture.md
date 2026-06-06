# System Architecture

## Overview

The AI-Assisted Radiology Explainer is designed to help patients better understand Chest and Bone X-Ray studies using both the radiology report and the associated X-Ray image.

The system combines report interpretation, image context, medical glossary generation, and doctor discussion questions to improve patient understanding after receiving imaging results.

Version 1 focuses on Chest and Bone X-Ray studies and does not perform independent medical diagnosis. The radiology report remains the primary source of clinical interpretation.


Version 1 focuses on report-based interpretation and does not perform direct X-Ray image analysis.

---

## Workflow

User Uploads:

* X-Ray Image
* Radiology Report PDF

↓

PDF Text Extraction (PyMuPDF)

↓

Report Type Classification
(Chest X-Ray or Bone X-Ray)

↓

Medical Finding Extraction

↓

Google Gemini Vision
(Image + Report Context)

↓

Patient-Friendly Explanation

↓

Medical Glossary Generation

↓

Doctor Discussion Question Generation

↓

Image Context Explanation

↓

Store Results in PostgreSQL

↓

Display Results in Streamlit Dashboard


---

## Components

### Frontend

* Streamlit
* File Upload Interface
* Results Dashboard
* Report History View

### Backend

* FastAPI
* API Endpoints
* Business Logic
* Validation and Error Handling

### AI Layer

* Google Gemini Vision API
* Report Interpretation
* Image Context Understanding
* Explanation Generation
* Glossary Generation
* Question Generation

### Database

* PostgreSQL
* Report Storage
* Analysis History

### PDF Processing

* PyMuPDF
* Text Extraction
* Report Parsing

### Image Processing

* X-Ray Image Upload
* Image Validation
* Image Context Extraction
* Image and Report Correlation

---

## Version 1 Supported Reports

* Chest X-Ray Reports
* Bone X-Ray Reports

---

## Future Expansion

* CT Report Support
* MRI Report Support
* Ultrasound Report Support
* Automated Region Highlighting
* Organ Visualization
* Multilingual Support
* Voice Explanations
