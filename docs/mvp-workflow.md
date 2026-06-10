# MVP Workflow

## Objective

The AI-Assisted Radiology Explainer helps patients understand Chest and Bone X-Ray studies by combining radiology report interpretation with X-Ray image context.

The system converts complex medical terminology into simple explanations while preserving the original meaning of the report. It is designed to improve patient understanding, health literacy, and doctor-patient communication after imaging studies.

---

## Supported Studies (Version 1)

### Chest X-Ray

Supported Findings:

* Cardiomegaly
* Pleural Effusion
* Pneumonia
* Pneumothorax

### Bone X-Ray

Supported Findings:

* Fracture
* Osteoarthritis
* Dislocation
* Joint Space Narrowing

---

## Workflow

### Step 1: Upload Study

Required Input:

* Radiology Report PDF

Optional Input:

* X-Ray Image

Output:

* Files received by the system

---

### Step 2: Extract Report Text

The system extracts text from the uploaded PDF using PyMuPDF.

Output:

* Raw report text

Example:

Findings:
Mild cardiomegaly noted.

Impression:
Mild enlargement of the cardiac silhouette.

---

### Step 3: Classify Report Type

The system determines whether the uploaded report belongs to:

* Chest X-Ray Report
* Bone X-Ray Report
* Other Medical Report

Output:

* Report category

Note:

Unsupported report types are not processed further by the MVP.

---

### Step 4: Extract Findings

The system identifies important findings present in the report.

Examples:

#### Chest Findings

* Cardiomegaly
* Pleural Effusion
* Pneumonia
* Pneumothorax

#### Bone Findings

* Fracture
* Osteoarthritis
* Dislocation
* Joint Space Narrowing

Output:

* List of detected findings

---

### Step 5: Generate Patient-Friendly Explanation

Google Gemini converts medical terminology into simple language.

Output:

* Simplified explanation

---

### Step 6: Generate Medical Glossary

Google Gemini identifies important medical terms and generates patient-friendly definitions.

Output:

* Medical glossary

---

### Step 7: Generate Doctor Discussion Questions

Google Gemini generates educational questions that patients may discuss with their healthcare provider.

Output:

* Doctor discussion questions

---

### Step 8: Save Analysis (Future)

Planned for a future MVP iteration.

Future Storage:

* X-Ray image
* Report text
* Findings
* Explanation
* Glossary
* Questions
* Image context

---

## Out of Scope

Version 1 will NOT:

* Perform independent medical diagnosis from X-Ray images
* Recommend treatments
* Prescribe medications
* Support CT reports
* Support MRI reports
* Replace healthcare professionals

---

## Why Not Just ChatGPT?

The system is specifically designed for radiology education and patient understanding.

It combines:

* X-Ray image understanding
* Radiology report interpretation
* Medical finding extraction
* Medical glossary generation
* Doctor discussion questions
* Image-to-report correlation
* Patient-friendly explanations

into a structured workflow focused on helping patients better understand their imaging studies.

---

## Success Criteria

The MVP will be considered successful if:

1. A user can upload a Chest or Bone X-Ray report.
2. A user can optionally upload an X-Ray image.
3. The system can extract report text from the uploaded PDF.
4. The system can classify the report type.
5. The system can extract supported findings from reports.
6. The system can generate patient-friendly explanations.
7. The system can generate a medical glossary.
8. The system can generate doctor discussion questions.
9. The system can reject unsupported report types.
