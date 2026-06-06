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

User uploads:

* X-Ray Image
* Radiology Report PDF

Input:

* Chest X-Ray Image + Report
  or
* Bone X-Ray Image + Report

Output:

* Study received by system

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

### Step 3: Identify Study Type

The system determines whether the uploaded study belongs to:

* Chest X-Ray
  or
* Bone X-Ray

Output:

* Study category

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

### Step 5: Analyze Image Context

Google Gemini Vision analyzes the uploaded X-Ray image together with the extracted report findings.

Example:

Report Finding:
Right middle lobe consolidation

Image Context:
The corresponding region of the right lung may be highlighted and explained to the user.

Output:

* Image context information
* Finding-to-image correlation

---

### Step 6: Generate Patient-Friendly Explanation

Google Gemini Vision converts medical terminology into simple language.

Example:

Finding:
Cardiomegaly

Explanation:
The report suggests that the heart appears larger than normal. This finding should be discussed with your healthcare provider for proper interpretation.

Output:

* Simplified explanation

---

### Step 7: Generate Medical Glossary

The system identifies difficult medical terms and generates patient-friendly definitions.

Example:

Cardiomegaly:
Enlargement of the heart.

Pleural Effusion:
Fluid buildup around the lungs.

Output:

* Medical glossary

---

### Step 8: Generate Doctor Discussion Questions

The system generates useful questions patients may ask their doctor.

Examples:

* What does this finding mean in my case?
* Do I need additional tests?
* Should this finding be monitored?
* Does this finding require follow-up imaging?

Output:

* Suggested doctor discussion questions

---

### Step 9: Save Analysis

The system stores:

* X-Ray image
* Report text
* Findings
* Explanation
* Glossary
* Questions
* Image context

Output:

* Analysis history

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
* Medical glossary generation
* Doctor discussion questions
* Image-to-report correlation
* Patient-friendly explanations

into a structured workflow focused on helping patients better understand their imaging studies.

---

## Success Criteria

The MVP will be considered successful if:

1. A user can upload a Chest or Bone X-Ray image and report.
2. The system can extract report text from the uploaded PDF.
3. The system can automatically identify important findings.
4. The system can generate patient-friendly explanations.
5. The system can generate medical glossary definitions.
6. The system can generate doctor discussion questions.
7. The system can provide image context related to report findings.
8. The user can view previously analyzed studies.
