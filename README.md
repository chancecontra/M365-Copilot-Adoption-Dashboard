# M365 Copilot Adoption Dashboard
Power BI Adoption Dashboard for M365 Copilot
## What it is?
## Functionalities
## Setup Instructions
### Registration of Graph API app
1. Sign in to the [Azure portal](https://portal.azure.com/). ![alt text](/Images/Setup1.png)
2. 3. Go to Microsoft Entra ID > App registrations. Screenshot showing the Entra app registration.
   <picture>/images/Setup1.png</picture>
4. Select + New Registration.
5. Enter a name. For example, use the Copilot Graph API name. Don't change any other settings and select Register.
6. Select API Permissions > + Add a permission. Screenshot that shows API permissions.
7. Select Microsoft Graph and configure permissions as follows:

Don't forget to add Grant Admin Consent for (your organization).
Select Certificates and secrets.
Select + New client secret.
Add a description and expiration (in line with your organization's policies), and then select Add.
Copy and paste the Secret to a text document such as Notepad.

Select Overview and copy and paste the application (client) ID and Directory (tenant) ID value to the same text document. Be sure to make a note of which GUID is for which value.


## Known Issues
