## Problem Statement
Clinics often face delays and inefficiencies during patient intake and triage, since many of them still rely on paper forms or have to manually enter each patient's information during check-ins. These processes lead to long wait times and missing or inconsistent information. Providers often have limited time to manually review each patient's current symptoms, insurance, and medical records. 

The objective of this project will be to propose a cloud-based patient intake and triage application that collects patient information digitally, performs prelinary assessment, and provides actionable insights to clinicians for faster and more accurate care.

### Users:

Patients: Fill out intake information upon arrival (personal information, symptoms, and relevant health history)

Front desk staff: Verify patient details and manage appointments

Nurses/Clinicians: See real-time queue, access structured patient data, triage levels, and patient details

## Data sources:
The application will store several types of data collected from patients and staff, and then the system processes:

1. Patient Demographic and Visit Information:
* Data type: JSON (structured)
* Fields: `patient_name`, `patient_DOB`, `patient_contact`, `patient_address` `visit_reason`
* Source: Entered by patient during digital intake form on web or app

2. Medical history and Symptoms:
* Data type: JSON (structured)
* Fields: `existing_conditions `, `allergies`, `medications`, `symptoms` `severity`, yes/no flags
* Optional vitals: if submitted by staff
* Source: Entered by patients during digital intake form on web or app, can be entered by staff with updates

3. Uploaded Documents
* Data type: Images (JPEG, PNG)
* Uploaded documents: ID cards, insurance cards (front and back)
* Source: Uploaded by patients on web or app

4. System-Generated Data
* Data type: JSON / database records
* Fields: `triage_score`(triage assigned: urgent / moderate / routine), `timestamps` (check-in time), `patient_status` (waiting, roomed, completed)
* Source: System-generated triage score and updated by staff interations

## Basic workflow:
1. Patient arrives at clinic and scans QR code or uses device provided by front desk

2. Patient completes digital check-in form, signs consent, and uploads ID/insurance

3. Patient answers symptom assessment (short triage survey)

4. Backend processes responses and assigns a triage level to patient(urgent / moderate / routine)

5. All data is stored in cloud storage + cloud database

6. The clinic dashboard updates automatically and shows:

* Patient name, date of birth, contact

* Triage level

* Symptom summary

* Waiting status

7. Nurse reviews triage level and either confirms or modifies it

8. Patient is called and roomed

9. The visit begins and care is provided