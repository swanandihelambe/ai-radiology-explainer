# Analysis History Design

## Objective

The Analysis History feature allows users to revisit previously generated report analyses without needing to re-upload the same report.

The feature improves usability while maintaining patient privacy within the MVP.

---

## Scope (MVP)

Users can:

* View previously generated analyses
* Review detected findings
* Review patient-friendly explanations
* Review medical glossary definitions
* Review doctor discussion questions

Users cannot:

* Modify previous analyses
* Upload analyses manually
* Download analyses
* Store patient-identifiable information

---

## Stored Information

Each analysis record contains:

* Analysis ID
* Timestamp
* Report Type
* Detected Findings
* Patient-Friendly Explanation
* Medical Glossary
* Doctor Discussion Questions

---

## Privacy Considerations

The MVP does not store:

* Patient Name
* Patient ID
* Hospital Number
* Phone Number
* Address
* Raw PDF Report
* Raw X-Ray Image

This approach minimizes privacy risks while still preserving generated educational content.

---

## History Screen Design

Example:

Analysis History

---

Chest X-Ray

June 13, 2026

Findings:

* Pleural Effusion (Small)

[View Analysis]

---

Chest X-Ray

June 11, 2026

Findings:

* Cardiomegaly (Mild)

[View Analysis]

---

## View Analysis

Selecting an analysis displays:

* Report Type
* Detected Findings
* Patient-Friendly Explanation
* Medical Glossary
* Doctor Discussion Questions

---

## Future Enhancements

* User Accounts
* Search and Filtering
* Report Downloads
* Secure Document Storage
* Encrypted Image Storage
* Audit Logging
* Consent Management

