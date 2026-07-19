# ZBIOMETRICS — SAP RAP Biometric User Identification System

A proof-of-concept SAP ABAP RAP application that identifies users 
by their fingerprint ID and displays their name instantly in a 
Fiori Elements List Report.

## Tech Stack
- SAP BTP ABAP Environment
- ABAP RESTful Application Programming Model (RAP)
- OData V4 UI Service
- SAP Fiori Elements (List Report)
- Eclipse ADT

## Architecture
Fingerprint Scanner (HID Mode)
↓
Fiori Elements UI (Search Field)
↓
OData V4 GET Request
↓
ZI_BiometricUser (CDS Root View)
↓
ZBIOMETRIC_USERS (DB Table)


## Project Objects

| Object | Type | Purpose |
|--------|------|---------|
| ZBIOMETRIC_USERS | DB Table | Stores fingerprint ID and user names |
| ZI_BIOMETRICUSER | CDS Root View | OData data model with UI annotations |
| ZUI_BIOMETRIC_USERS | Service Definition | Exposes CDS as OData service |
| ZUI_BIOMETRIC_USERS_V4 | Service Binding | OData V4 UI endpoint |
| ZCL_SEED_BIOMETRIC_USERS | ABAP Class | One-time test data seeder |

## How to Deploy
1. Create package `ZBIOMETRICS_USERS` in Eclipse ADT
2. Create DB table from `src/db/`
3. Run seeder class once (F9) to insert test data
4. Create CDS view from `src/cds/`
5. Create Service Definition from `src/service/`
6. Create Service Binding → Activate → Publish → Preview

## How to Test
1. Open Fiori Preview from Service Binding
2. Paste a Fingerprint ID from `test/test_fingerprint_ids.txt`
3. Press Enter
4. User's First Name and Last Name appear in the grid

## Developer
- **Name:** Sarbajit Samantaray
- **GitHub:** [Sarbajit-09](https://github.com/Sarbajit-09)
- **LinkedIn:** [sarbajit-samantaray](https://linkedin.com/in/sarbajit-samantaray-884803294)
- **University:** Centurion University of Technology and Management (CUTM)
