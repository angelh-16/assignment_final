# Architecture & Implementation Plan

## Server mapping

   | Layer          | Service (Cloud)                              | Role in Solution                                           | Related Modules           |
   |----------------|----------------------------------------------|------------------------------------------------------------|---------------------------|
   | Frontemd/API   | Cloud Run                                    | Hosts the patient intake form and receives submissions from browser/app clients | Module 10       |
   | Storage        | GCP Cloud Storage                            | Stores patient/provider uploaded images (ID, insurance cards or attachments) | Module 6      |
   | Compute        | Cloud Function                               | Computes the triage score based on symptoms and inputs and sends to SQL    | Module 5       |
   | Database/SQL   | Cloud SQL                                    | Stores structured intake data, triage results, timestamps, visit status| Module 7 |
   | Analytics/AI   | Python analytics                             | Generates basic reports and insights from intake and triage data     | Module 9       |
   | Network/Access | GCP Network settings and Firewall            | Controls access to VM, Cloud SQL, functions and storage    | Module 4       |


## Data flow narrative
1. Patient uses browser or app to access the intake form
2. Form submission travels through the Internet to GCP
3. Traffic reaches the Flask Web App
4. Flask app stores intake data (JSON) in Cloud SQL, stores uploaded images (JPEG/PNG) in Cloud Storage and sends symptom inputs to the triage function
5. Triage function analyzes patient’s symptoms and returns a triage score (urgent, moderate, routine)
6. Flask sends triage result back to Cloud SQL
7. Staff Dashboard queries Cloud SQL to displays patient info, triage category, waiting status, timestamp
9. Clinicians confirms or modify triage assessment
10. Patient status of appointment is updated by staff

## Security, identity, and governance basics

## Cost and operational considerations