# M365 Copilot Adoption Dashboard
Power BI Adoption Dashboard for M365 Copilot
## What it is?
## Functionalities
## Setup Instructions
### Registration of Graph API app
1. Sign in to the [Azure portal](https://portal.azure.com/). 
2. Go to Microsoft Entra ID > App registrations. 
![Screenshot showing the Entra app registration.](/Images/Setup1.png)
3. Select + New Registration.
4. Enter a name. For example, use the Copilot Graph API name. Don't change any other settings and select Register.
5. Select API Permissions > + Add a permission.
 ![Screenshot that shows API permissions.](/Images/Setup2.png)  
6. Select Microsoft Graph and configure permissions as follows:
![Screenshot showing permissions.](/Images/Setup3.png)
7. Don't forget to add Grant Admin Consent for (your organization).
8. Select Certificates and secrets.
9. Select + New client secret.
10. Add a description and expiration (in line with your organization's policies), and then select Add.
11. Copy and paste the Secret to a text document such as Notepad.
![Screenshot showing permissions.](/Images/Setup4.png)
12. Select Overview and copy and paste the application (client) ID and Directory (tenant) ID value to the same text document. Be sure to make a note of which GUID is for which value.
![Screenshot showing permissions.](/Images/Setup5.png)


## Known Issues
