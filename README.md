# M365 Copilot Adoption Dashboard
Power BI Adoption Dashboard for M365 Copilot.<br/>
Developed by [Sead Borovina](www.linkedin.com/in/seadb)
## What it is?
This is custom M365 Copilot Adoption Dashboard that uses Graph API (in beta) to grab data from your M365 tenant.<br/> Some organizations, for various reasons, found existing reports in M365 Admin Portal, Viva insights or Copilot Dashboard not suitable for the purpose of driving adoption, hence there was the need for the custom dashboard. I developed this dashboard working with organizations that were in this position, and needed insights on the adoption of M365 Copilot. Feedback and requirements provided by those organizations have been used as an input for the dashboard, within restrictions that provide Graph API at the moment.
Now you can use this dashboard for M365 Copilot Adoption analysis in your tenant or as a starting point to further develop your own custom dashboard. <br/>
Please provide your feedback or ideas via this [form](https://forms.office.com/r/cFsEWFJ3yD). 
## Overview and Functionalities
This dashboard contains four pages:
1. Overview
2. Users
3. Readiness
4. Organization
### 1. Overview and History
![Screenshot showing overview.](/Images/Dashboard1.png)
1. Card shows active users % and total numer of active users in the last 30 days (Active users # is the total number of users with Copilot licence in your organization who tried a user-initiated Microsoft 365 Copilot feature).
2. Shows user distribution per Copilot usage in different apps (Where the prompt has been triggered from, have in mind single user can run Copilot in different tools so that means same user can contribute to Word and Excel values in the chart)
3. Top 10 departments in the organization per number of active users (Departments are taken from Entra ID field department)
4. Slicer for Copilot details in Chart 7.
5. Slicer to show total number of licences or not in Chart 7. (purple line)
6. Buttons to select if you want to see absolute or % usage values (numbers or %) in Chart 7.
7. 6 months aggregated historical overview of active users. Axis slider enables zoom in. When using % you can drill down on daily level.
## Setup Instructions
You need to do following steps:
1. Register Graph API app
2. Install latest version of Power BI desktop and configure it
3. Download and run template

### 1. Registration of Graph API app
1. Sign in to the [Azure portal](https://portal.azure.com/).
   (For these actions you need at least Cloud Application Administrator role.)
3. Go to **Microsoft Entra ID > App registrations**. 
![Screenshot showing the Entra app registration.](/Images/Setup1.png)
4. Select **+ New Registration**.
5. Enter a name. For example, use the **Copilot Graph API** name. Don't change any other settings and select **Register**.
6. Select **API Permissions > + Add a permission**.
 ![Screenshot that shows API permissions.](/Images/Setup2.png)  
7. Select **Microsoft Graph** and configure permissions as follows:
![Screenshot showing permissions.](/Images/Setup3.png)
8. Don't forget to add **Grant Admin Consent for (your organization)**.
9. Select **Certificates and secrets**.
10. Select **+ New client secret**.
11. Add a description and expiration (in line with your organization's policies), and then select **Add**.
12. Copy and paste the **Secret** to a text document such as Notepad.
![Screenshot showing secret.](/Images/Setup4.png)
13. Select **Overview** and copy and paste the application (client) ID and Directory (tenant) ID value to the same text document. Be sure to make a note of which GUID is for which value.
![Screenshot showing tenant ID and client ID.](/Images/Setup5.png)

### 2. Get Latest Version of Power BI Desktop and configure
1. If you don't have it, you can download it from [here](https://www.microsoft.com/en-us/download/details.aspx?id=58494&msockid=3d302a18b1e16b4b0f433bb7b5e16d2d)
2. Once installed start Power BI desktop. Go to **File > Options and Settings > Options**
3. Enable **Text Slicer Visual** under **Preview features** (you will have to restart app)
![Screenshot showing Power BI configuration.](/Images/Setup6.png)

### 3. Download and run the template (.pbit)

## Known Issues
