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

<img src="https://raw.githubusercontent.com/Jamaal239/servicenow-vdi-catalog-item/main/01_Catalog_Item_Definition.png" width="100%">

### 02. Business Justification Variable
Configuration of the multi-line text input field establishing validation logic for tracking required end-user business cases.

<img src="https://raw.githubusercontent.com/Jamaal239/servicenow-vdi-catalog-item/main/02_Variable_Justification.png" width="100%">

### 03. Access Level Variable Setup
Design of the Select Box (dropdown menu) variable establishing the underlying script variable name `access_level`.

<img src="https://raw.githubusercontent.com/Jamaal239/servicenow-vdi-catalog-item/main/03_Variable_Access_Level.png" width="100%">

### 04. Dropdown Choice Mapping
Database architecture configuration mapping display values to logical data keys with explicit ordering numbers (100 and 200) to enforce sorting hierarchy.

<img src="https://raw.githubusercontent.com/Jamaal239/servicenow-vdi-catalog-item/main/04_Dropdown_Choices.png" width="100%">

### 05. Live Form Front-End Testing
End-to-end verification via the ServiceNow Service Portal interface, showcasing a fully responsive user form with placeholder text data validated and ready for checkout.

<img src="https://raw.githubusercontent.com/Jamaal239/servicenow-vdi-catalog-item/main/05_Catalog_Item_Testing.png" width="100%">

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
