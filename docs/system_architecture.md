# System Architecture

## Overview

The AI-Assisted Radiology Explainer is designed to help patients better understand Chest and Bone X-Ray studies using radiology reports and optional X-Ray image uploads.

The system converts complex radiology terminology into patient-friendly explanations while generating medical glossary definitions, doctor discussion questions, and structured finding extraction.

Version 1 focuses on report-based interpretation and does not perform independent medical diagnosis or direct X-Ray image analysis.

---

## Workflow

User Uploads:

* Radiology Report PDF (Required)
* X-Ray Image (Optional)

↓

PDF Text Extraction (PyMuPDF)

↓

Report Type Classification

↓

Medical Finding Extraction

↓

Google Gemini API

├─ Patient-Friendly Explanation

├─ Medical Glossary Generation

└─ Doctor Discussion Question Generation

↓

Display Results in Streamlit Dashboard

---

## Components

### Frontend

* Streamlit
* File Upload Interface
* Results Dashboard

### Backend

* Python Application Logic
* Validation and Error Handling
* Report Classification
* Finding Extraction

### AI Layer

* Google Gemini API
* Report Interpretation
* Patient-Friendly Explanation Generation
* Medical Glossary Generation
* Doctor Discussion Question Generation

### Database (Future)

* PostgreSQL
* Report Storage
* Analysis History

### PDF Processing

* PyMuPDF
* Text Extraction
* Report Parsing

### Image Processing

* Optional X-Ray Image Upload
* Image Validation

Future:

* Image Context Extraction
* Image and Report Correlation

---

## Version 1 Supported Reports

### Chest X-Ray Reports

Supported Findings:

* Cardiomegaly
* Pleural Effusion
* Pneumonia
* Pneumothorax

### Bone X-Ray Reports

Supported Findings:

* Fracture
* Osteoarthritis
* Dislocation
* Joint Space Narrowing

---

## Current MVP Features

* PDF Report Upload
* Optional X-Ray Image Upload
* PDF Text Extraction
* Report Type Classification
* Medical Finding Extraction
* Patient-Friendly Explanation Generation
* Medical Glossary Generation
* Doctor Discussion Question Generation
* Unsupported Report Detection

---

## Future Expansion

* Finding Severity Detection
* Analysis History Tracking
* PostgreSQL Integration
* Image-to-Report Contextual Analysis
* AI-Based Report Classification
* CT Report Support
* MRI Report Support
* Ultrasound Report Support
* Automated Region Highlighting
* Organ Visualization
* Multilingual Support
* Voice Explanations
