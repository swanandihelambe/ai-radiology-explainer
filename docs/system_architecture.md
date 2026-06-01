# System Architecture

## Overview

The AI-Assisted X-Ray Report Explainer is designed to help patients understand Chest and Bone X-Ray reports by converting complex medical terminology into patient-friendly explanations.

Version 1 focuses on report-based interpretation and does not perform direct X-Ray image analysis.

---

## Workflow

User Uploads X-Ray Report PDF

↓

PDF Text Extraction (PyMuPDF)

↓

Report Type Classification
(Chest X-Ray or Bone X-Ray)

↓

Medical Finding Extraction

↓

Google Gemini API

↓

Patient-Friendly Explanation

↓

Medical Glossary Generation

↓

Doctor Discussion Question Generation

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

* Google Gemini API
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

---

## Version 1 Supported Reports

* Chest X-Ray Reports
* Bone X-Ray Reports

---

## Future Expansion

* CT Report Support
* MRI Report Support
* Ultrasound Report Support
* Organ Visualization
* Multilingual Support
* Voice Explanations
