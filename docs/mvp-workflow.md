# MVP Workflow

## Objective

The AI-Assisted X-Ray Report Explainer helps patients understand Chest and Bone X-Ray reports by converting complex medical terminology into simple explanations while preserving the original meaning of the report.

---

## Supported Reports (Version 1)

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

## Workflow

### Step 1: Upload Report

User uploads an X-Ray report PDF.

Input:

* Chest X-Ray Report PDF
* Bone X-Ray Report PDF

Output:

* PDF received by system

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

### Step 3: Identify Report Type

The system determines whether the uploaded report belongs to:

* Chest X-Ray
  or
* Bone X-Ray

Output:

* Report category

---

### Step 4: Extract Findings

The system identifies important findings present in the report.

Examples:

Chest:

* Cardiomegaly
* Pleural Effusion
* Pneumonia
* Pneumothorax

Bone:

* Fracture
* Osteoarthritis
* Dislocation
* Joint Space Narrowing

Output:

* List of detected findings

---

### Step 5: Generate Patient-Friendly Explanation

Google Gemini converts medical terminology into simple language.

Example:

Finding:
Cardiomegaly

Explanation:
The report suggests that the heart appears larger than normal. This finding should be discussed with your healthcare provider for proper interpretation.

Output:

* Simplified explanation

---

### Step 6: Generate Medical Glossary

The system identifies difficult medical terms and generates definitions.

Example:

Cardiomegaly:
Enlargement of the heart.

Pleural Effusion:
Fluid buildup around the lungs.

Output:

* Medical glossary

---

### Step 7: Generate Doctor Discussion Questions

The system generates useful questions patients may ask their doctor.

Examples:

* What does this finding mean in my case?
* Do I need additional tests?
* Should this finding be monitored?

Output:

* Suggested doctor discussion questions

---

### Step 8: Save Analysis

The system stores:

* Report text
* Findings
* Explanation
* Glossary
* Questions

Output:

* Analysis history

---

## Out of Scope

Version 1 will NOT:

* Diagnose diseases
* Recommend treatments
* Interpret X-Ray images
* Support CT reports
* Support MRI reports
* Replace healthcare professionals

---

## Success Criteria

The MVP will be considered successful if a user can:

1. Upload a Chest or Bone X-Ray report.
2. Extract report text.
3. Identify important findings.
4. Generate patient-friendly explanations.
5. Generate glossary terms.
6. Generate doctor discussion questions.
7. View previously analyzed reports.

