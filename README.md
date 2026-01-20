# DynFOTech-Altinn

This project is mainly focused on **VAT return with direct submission to Altinn in D365FO**.  

In the first part, we provide the package **"NO VAT return Altinn v4 ID854065"**, which can be used to import predefined data for **Electronic messages** in D365FO.

## Import Steps in D365FO

1. Open the relevant legal entity in D365FO.
2. Go to **Workspaces > Data management**.
3. Select **Import** and create a new import project:
   - Provide a **Group name** and **Description**.
4. Click **Add file** and upload the ZIP file.
5. After upload, 16 data entities will appear in the entity list.
6. Select **Import** to execute the job.
   <img width="994" height="783" alt="image" src="https://github.com/user-attachments/assets/3252166f-6f6b-470c-b5b2-287d2122d6db" />


## Post-Import Setup

1. Navigate to:  
   `Tax > Setup > Electronic messages > Web applications`
2. Locate the record named **NO ID-Porten** and verify the following:

   **Authorization URL path:** `https://login.idporten.no/authorize`  
   **Token URL path:** `https://idporten.no/token`

   > Use these URLs for production environments as of 20.01.2026.
