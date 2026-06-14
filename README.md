# ServiceNow Service Catalog: Cloud-Based Virtual Workstation (VDI) Request Item

A custom-built ServiceNow Service Catalog item designed to streamline and automate corporate requests for cloud-based virtual desktop infrastructure (VDI). This project configures a user-facing front-end form with data validation and binds it directly to an automated backend fulfillment process engine.

## Features Configured
* **Global Scope Integration:** Configured cleanly within the Global application scope for standard enterprise deployment.
* **Dynamic User Input Variables:**
  * A multi-line string text field capturing detailed business justifications.
  * A custom Select Box choice variable managing access tier classifications.
* **Data-Driven Dropdown Architecture:** Structured backend database keys (standard / admin) mapped cleanly to user-friendly UI display labels (Standard Access / Administrator Access).
* **Process Engine Mapping:** Linked directly to the Service Catalog item request Flow Engine to kick off automated workflows immediately upon submission.

---

## Project Architecture & Verification

### 01. Catalog Item Definition
The initial baseline configuration detailing the catalog routing, categorical assignment under "Can We Help You?", and user storefront presentation details.

<img width="1920" height="949" alt="01_Catalog_Item_Definition" src="https://github.com/user-attachments/assets/a7088d5c-c9b5-4680-a0c7-587bed61a434" />


### 02. Business Justification Variable
Configuration of the multi-line text input field establishing validation logic for tracking required end-user business cases.

<img width="1920" height="950" alt="02_Variable_Justification" src="https://github.com/user-attachments/assets/01a6f181-5545-4f03-b3b7-16d6d09854d9" />


### 03. Access Level Variable Setup
Design of the Select Box (dropdown menu) variable establishing the underlying script variable name `access_level`.

<img width="1920" height="940" alt="03_Variable_Access_Level" src="https://github.com/user-attachments/assets/b4db1d9c-355f-41c9-ac28-9e52b46f6791" />

### 04. Dropdown Choice Mapping
Database architecture configuration mapping display values to logical data keys with explicit ordering numbers (100 and 200) to enforce sorting hierarchy.

<img width="1920" height="949" alt="04_Dropdown_Choices" src="https://github.com/user-attachments/assets/646b111c-804a-42ae-b22f-2b940f8ae6d4" />


### 05. Live Form Front-End Testing
End-to-end verification via the ServiceNow Service Portal interface, showcasing a fully responsive user form with placeholder text data validated and ready for checkout.

<img width="1920" height="947" alt="05_Catalog_Item_Testing" src="https://github.com/user-attachments/assets/c5f60b54-9a33-4121-9624-f78e402a7f97" />


---

## Technical Specifications

| Field Asset | Configuration Property | Applied Value |
| :--- | :--- | :--- |
| **Catalog Item** | Name | Request Virtual Desktop (VDI) Access |
| | Catalog / Category | Service Catalog / Can We Help You? |
| **Variable 1** | Type / Name | Multi Line Text / business_justification |
| **Variable 2** | Type / Name | Select Box / access_level |
| **Choices** | Text / Value (Order 100) | Standard Access / standard |
| | Text / Value (Order 200) | Administrator Access / admin |
| **Process Engine**| Flow | Service Catalog item request |

---

## How to Deploy This in a PDI (Personal Developer Instance)
1. Navigate to **Service Catalog > Catalog Definitions > Maintain Items** and select **New**.
2. Configure the item details using the parameters defined in the Technical Specifications table above.
3. Utilize the **Variables** related list to construct the user inputs.
4. Open the `access_level` variable record and use the **Question Choices** related list to map the specific option keys and weights.
5. Pivot to the **Process Engine** tab and bind the standard catalog fulfillment flow to finish routing.
