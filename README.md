This project is focused on VAT return with direct submission to Altinn in D365FO.

The solution supports end-to-end handling of the Norwegian VAT return
(MVA-melding), including:

-   VAT declaration generation
-   Excel preview
-   Direct submission to Altinn
-   ID-Porten authentication
-   Feedback and validation result import

  --------------------------------------------
  
 <br> Electronic Reporting Configuration Package
  --------------------------------------------
<br>
The first part of this repository delivers the complete Electronic
Reporting (ER) configuration set required to enable Norwegian VAT Return
integration with Altinn.<br>

All configuration files are provided as .xml (except the folder
structure).<br>

  ------------------
  Folder Structure
  ------------------

Altinn <br>
├── Electronic Messages<br>
└── Tax Declaration<br>

  ------------------------
  <br>1. Electronic Messages
  ------------------------

Contains configurations required to manage communication with Altinn
using the Electronic Messages framework in D365FO.<br>

Included Configurations:

-   Electronic Messages framework model (47)
-   Electronic Messages framework model (51)
-   Altinn VAT model mapping (47.9)
-   Altinn VAT authorization format (NO) (51.10)
-   Altinn VAT import Altinn token format (NO) (47.4)
-   Altinn VAT import feedback status format (NO) (47.4)
-   Altinn VAT import ID-Porten token format (NO) (47.4)
-   Altinn VAT import instance format (NO) (47.4)
-   Altinn VAT import validation result format (NO) (47.5)
-   Altinn VAT web request headers format (NO) (47.6)<br>

These configurations handle:

-   Authentication (ID-Porten / Altinn)
-   Authorization
-   Web request header construction
-   Submission orchestration
-   Feedback status retrieval
-   Validation result processing<br>

  --------------------
  <br>2. Tax Declaration
  --------------------

Contains VAT declaration models and formats used to generate the
official Norwegian VAT Return.

Included Configurations:

-   Tax declaration model (112)
-   Tax declaration model (180)
-   Tax declaration model mapping (182.359)
-   Altinn VAT interoperation (NO) (112.7)
-   VAT Declaration XML (NO) (112.72)
-   VAT Declaration Excel (NO) (112.72.61)<br>

These configurations manage:

-   VAT data extraction
-   XML generation for Altinn
-   Excel preview format
-   Interoperation between Tax module and Electronic Messages<br>

  ------------------------------------
  <br>Import ER Configurations in D365FO
  ------------------------------------

1.  Navigate to: Organization administration > Electronic reporting >
    Configurations

2.  Click: Exchange > Load XML file <img width="915" height="183" alt="image" src="https://github.com/user-attachments/assets/07d4c96e-c390-4e08-aa3a-3a74a67e8746" />

3.  Import configurations in this order:

    -   First: All files under Tax Declaration
    -   Second: All files under Electronic Messages

4.  Validate that “Default for model mapping” is activated for:

    -   Altinn VAT model mapping
    -   Tax declaration model mappingles under Tax Declaration
   -Second: All files under Electronic Messages

3.  Validate "Default for model mapping" is activated for:
   -Altinn VAT model mapping
   -Tax declaration model mapping<br>

  -------------------------------------------------
  <br>Data Package Import (Electronic Messages Setup)
  -------------------------------------------------


In the second part, we provide the package **"NO VAT return Altinn v4 ID854065"**, which can be used to import predefined data for **Electronic messages** in D365FO.

  -------------------
  <br>Import Setup
  -------------------

1. Open the relevant legal entity in D365FO.
2. Go to **Workspaces > Data management**.
3. Select **Import** and create a new import project:
   - Provide a **Group name** and **Description**.
4. Click **Add file** and upload the ZIP file.
5. After upload, 16 data entities will appear in the entity list.
6. Select **Import** to execute the job.
   <img width="994" height="783" alt="image" src="https://github.com/user-attachments/assets/3252166f-6f6b-470c-b5b2-287d2122d6db" />


  -------------------
  <br>Post-Import Setup
  -------------------

1. Navigate to:  
   `Tax > Setup > Electronic messages > Web applications`
2. Locate the record named **NO ID-Porten** and verify the following:

   **Authorization URL path:** `https://login.idporten.no/authorize`  
   **Token URL path:** `https://idporten.no/token`

   > Use these URLs for production environments as of 20.01.2026.


  --------
  <br>AUTHOR
  --------

Alireza Eshaghzadeh 
