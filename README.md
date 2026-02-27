# Portfolio

### Carl Frances

Full Stack Web Developer | Software QA Automation Engineer

#### :wave: About me 

I am a Computer Science graduate with professional experience in Full Stack Development, Machine Learning Systems, and QA Automation Engineering. I specialize in building reliable web applications and ensuring software quality through structured manual and automated testing.

[My Linkedin profile](https://www.linkedin.com/in/carl-francess-tudtud-12266934a/)

Currently, I work as a Software QA Automation Engineer, managing and testing Electronic Medical Record (EMR) systems used by multiple agencies.

### 🏢 Professional Experience

#### 🔹 Strongwill IT Solutions — Software QA Automation Engineer  
**February 2025 – Present**

- Developed QA automation scripts using Selenium + Robot Framework  
- Managed and tested EMR systems used by multiple agencies  
- Created and executed structured test cases and regression plans  
- Validated healthcare data accuracy and role-based access  
- Supported deployment testing and post-release validation  

#### 🔹 Lapanday Foods Corporation — Full Stack & ML Developer  
**December 2022 – January 2024**

- Developed Image-Based Plant Disease Detection system  
- Built mobile (user-side) and web (admin-side) applications  
- Integrated SVM Machine Learning model using Python, TensorFlow, and Keras  

#### 🔹 Dadiangas North Elementary School — Full Stack Developer Intern  
**February 2024 – April 2024**

- Developed Library Management System  
- Implemented automated Dewey Decimal Classification generator  
- Built transaction management and reporting modules  

---

### 🛠 Technical Skills

#### 💻 Programming
- JavaScript  
- PHP (Laravel)  
- Python (Automation & ML)  
- HTML & CSS  
- MySQL  
- React  

#### 🧪 QA & Automation
- Manual Testing  
- Test Case Creation  
- Regression Testing  
- Selenium  
- Robot Framework  
- API Testing (Postman)  

---

### 🏥 EMR System QA Case Study

#### 📌 Project Overview
Electronic Medical Record (EMR) system used by multiple agencies to manage patient records, workflows, and reporting.

#### 🎯 Responsibilities
- Conducted end-to-end functional testing  
- Verified role-based access (Admin, Medical Staff, Agency Users)  
- Performed regression testing before deployment  
- Validated patient data integrity and reporting accuracy  
- Identified and documented critical system defects  

---

### 🤖 QA Automation Sample Implementation

Below are sample automation scripts demonstrating my QA automation approach.

#### 🔹 Sample Automation Syntax: Selenium with Python

#### 📁 visit_note_esign_test.robot

```robot
*** Settings ***
Library    SeleniumLibrary

*** Variables ***
${URL}                https://example-emr.com
${BROWSER}            Chrome
${ASSIGNED_USER}      nurse_anna
${ASSIGNED_PASS}      password123
${UNASSIGNED_USER}    nurse_mark
${UNASSIGNED_PASS}    password123
${PATIENT_NAME}       John Doe
${AGENCY_NAME}        Agency A

*** Test Cases ***
Assigned Staff Can E-Sign Visit Note
    Login Browser    ${ASSIGNED_USER}    ${ASSIGNED_PASS}
    Select Agency    ${AGENCY_NAME}
    Search Patient   ${PATIENT_NAME}
    Plot Visit Note
    Fill Visit Note
    Save And Validate
    E-Sign Visit Note
    Verify E-Sign Success
    Close Browser

Unassigned Staff Cannot E-Sign Visit Note
    Login Browser    ${UNASSIGNED_USER}    ${UNASSIGNED_PASS}
    Select Agency    ${AGENCY_NAME}
    Search Patient   ${PATIENT_NAME}
    Open Existing Visit Note
    Attempt E-Sign Visit Note
    Verify E-Sign Not Allowed
    Close Browser
```
### 📁 keywords.robot

```robot
*** Keywords ***

Login Browser
    [Arguments]    ${USERNAME}    ${PASSWORD}
    Open Browser    ${URL}    ${BROWSER}
    Input Text      id=username    ${USERNAME}
    Input Text      id=password    ${PASSWORD}
    Click Button    id=loginBtn
    Wait Until Page Contains    Dashboard

Select Agency
    [Arguments]    ${AGENCY}
    Click Element    id=agencyDropdown
    Click Element    xpath=//option[text()='${AGENCY}']
    Wait Until Page Contains    Agency Dashboard

Search Patient
    [Arguments]    ${PATIENT}
    Input Text      id=searchPatient    ${PATIENT}
    Click Button    id=searchBtn
    Wait Until Page Contains    ${PATIENT}

Plot Visit Note
    Click Button    id=plotVisitBtn
    Wait Until Page Contains    Visit Note Form

Fill Visit Note
    Input Text      id=chiefComplaint    Fever and cough
    Input Text      id=diagnosis         Acute Viral Infection
    Input Text      id=prescription      Paracetamol 500mg

Save And Validate
    Click Button    id=saveVisitBtn
    Wait Until Page Contains    Visit Note Saved Successfully

E-Sign Visit Note
    Click Button    id=esignBtn
    Input Text      id=esignPassword    password123
    Click Button    id=confirmESignBtn

Verify E-Sign Success
    Wait Until Page Contains    Visit Note E-Signed Successfully

Open Existing Visit Note
    Click Element    xpath=//button[text()='Open Visit Note']
    Wait Until Page Contains    Visit Note Details

Attempt E-Sign Visit Note
    Click Button    id=esignBtn

Verify E-Sign Not Allowed
    Wait Until Page Contains    You are not the assigned staff for this visit
```
