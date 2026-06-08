# AI-Assisted Radiology Explainer

AI-Assisted Radiology Explainer is a healthcare AI project that helps patients better understand Chest and Bone X-Ray studies using both the radiology report and the associated X-Ray image.

Radiology reports often contain complex medical terminology that can be difficult for non-medical users to interpret. This project focuses on converting report findings into patient-friendly explanations while providing image context, medical glossary support, and doctor discussion questions.

## Planned Features

* Radiology report PDF upload
* Optional X-Ray image upload
* Report type classification
* Medical finding extraction
* Simplified AI-generated explanations
* Medical term glossary
* Doctor discussion questions
* Image-to-report contextual explanation
* Visual finding interpretation support
* Report history tracking


## Version 1 Scope

Required Input:

* Radiology Report PDF

Optional Input:

* X-Ray Image

Supported Report Types:

* Chest X-Ray Reports
* Bone X-Ray Reports

## Tech Stack

* Python
* Streamlit
* FastAPI
* PostgreSQL
* Google Gemini API
* AWS

## Current Progress

### Completed

* Project planning
* Problem statement definition
* System architecture design
* Initial Chest X-Ray domain research
* Initial Bone X-Ray domain research

### In Progress

* Sample report collection
* Medical terminology mapping
* Prompt design for AI explanations
* X-Ray image integration planning

### Upcoming

* PDF text extraction
* Report type classification
* AI explanation generation
* Medical glossary generation
* Doctor discussion questions

## Why Not Just ChatGPT?

This project is designed specifically for radiology education and patient understanding.

It combines:

* X-Ray image understanding
* Radiology report interpretation
* Medical glossary generation
* Doctor discussion questions
* Patient-friendly explanations

into a structured workflow focused on helping patients better understand their imaging studies.

## Project Status

Currently in MVP development.

Implemented Features:

* PDF report upload
* Optional X-Ray image upload
* PDF text extraction
* Report type classification
* AI-generated patient-friendly explanations

In Progress:

* Medical glossary generation
* Doctor discussion questions
* Image-to-report contextual analysis

## Disclaimer

This project is intended for educational purposes only. It does not provide medical diagnoses and should not replace professional medical advice.
