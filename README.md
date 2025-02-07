# M365 Copilot Adoption Dashboard
Power BI Adoption Dashboard for M365 Copilot.<br/>
Developed by [Sead Borovina](https://www.linkedin.com/in/seadb) </br>
Last version 17 Jan 2025
## What it is?
This is custom M365 Copilot Adoption Dashboard that uses Graph API (in beta) to grab data from your M365 tenant.<br/> Some organizations, for various reasons, found existing reports in M365 Admin Portal, Viva insights or Copilot Dashboard not suitable for the purpose of driving adoption, hence there was the need for the custom dashboard. I developed this dashboard working with organizations that were in this position and needed insights into the adoption of M365 Copilot. Feedback and requirements provided by those organizations have been used as an input for the dashboard, within restrictions that provide Graph API at the moment (this dashboard is not using Audit Logs as data source).
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
1. Card shows active users % and total number of active users in the last 30 days (Active users # is the total number of users with Copilot license in your organization who tried a user-initiated Microsoft 365 Copilot feature).
2. Shows user distribution per Copilot usage in different apps (Where the prompt has been triggered from, have in mind single user can run Copilot in different tools so that means same user can contribute to Word and Excel values in the chart)
3. Top 10 departments in the organization per number of active users (Departments are taken from Entra ID field department)
4. Slicer for Copilot details in Chart 7.
5. Slicer to show total number of licenses or not in Chart 7. (purple line)
6. Buttons to select if you want to see absolute or % usage values (numbers or %) in Chart 7.
7. 6 months aggregated historical overview of active users. Axis slider enables zoom in. When using % you can drill down on daily level.
### 2. Users
This page shows details about users with assigned M365 Copilot license.
![Screenshot showing overview.](/Images/Dashboard2.png)
1. Card shows M365 Copilot enabled users (with license assigned) [*See known issues](## Known Issues)
2. Enabled users are distributed in 4 sub categories:
   a. Active Users - the ones that had at least 1 prompt in any of the M365 Copilot interfaces in the last 30 days </br>
   b. Churned Users - users that had at least 1 prompt in any of the M365 Copilot interfaces in between 30 and 60 days from last refresh time </br>
   c. Lost Users - users that had at least 1 prompt in any of the M365 Copilot interfaces 60+ days ago from last refresh time </br>
   d. Enabled but never active - number of users who were assigned M365 Copilot license but they never used it (not a single prompt) </br>
3. Slicer to select mentioned categories and show the list in table 7.
4. Keyword filter (if you are looking for particular user by name)
5. Slicer to show Champion material (most engaged users by the number of apps where they use Copilot in) In essence they have maturity rating above 5 (see definition for Maturity rating on the page)
6. Filter per Company, Department or Country - taken from Entra ID.
7. Table with names and other details based on selection. You can select each user individually to see details in cards 8.
8. Cards that show the last date of usage for M365 Copilot in each tool (if user is active). For inactive users, card will be marked in red without any date. [*See known issues](## Known Issues)
### 3. Readiness
This page shows details about all users from Microsoft Entra ID (excluding service and external accounts) withouth M365 Copilot License assigned.
![Screenshot showing overview.](/Images/Dashboard3.png)
1. Card shows number of Entra ID users (excluding service and external accounts) without M365 Copilot License assigned.
2. Users are distributed in 4 sub categories based how "good" are they in using M365 services (as you want to assign Copilot license to user that is already mature user of M365 rather than to someone who is not yet there):
   a. Priority A - 11+ points for M365 usage (definition is provided on the page itself)
   b. Priority B - 4.5 to 10.5 points
   c. Priority C - less than 4.5 points
   d. Priority D - 0 points (you really don't want to assign Copilot license to these users)
3. Slicer to select mentioned categories and show the list in table 4.
4. Table with names and other details based on selection. You can select each user individually to see details in cards 5.
5. Cards that show per user usage of some of the M365 Features (Apps - if a user is viewing/editing files in any of apps, Teams Activity - what user does in Teams, OneDrive Activity - what users do with files in their OneDrive)
### 4. Organization and insights
This page shows really some overviews per department/company in matrix visual for easier comparison between departments.
![Screenshot showing overview.](/Images/Dashboard4.png)
1. Company and Department x usage % per app for Copilot - gives you an overview of where the most activity in M365 world happens across the organization
2. Top 10 users overall by how broadly they use Copilot (not per number of prompts, just per entry points)
## Setup Instructions
You need to take following steps:
1. Register Graph API app
2. Install the latest version of Power BI desktop and configure it
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
1. Download [template](/M365_Copilot_Adoption_Dashboard_template.pbit).
2. Start template.
3. Enter required parameters that you collected in step 1. of the setup.
![Screenshot showing template.](/Images/Start1.png)
4. Wait for data to load.
5. Replace **Insert Company Logo** image with real logo of your organization. Look for how to insert image in Power BI desktop if you don't know how.</br>
![Screenshot showing logo.](/Images/Start2.png)
7. **REQUIRED**: Save your file as PBIX. Remember this is just a template loaded with data - until you save the file as pbix.
8. Optional: Publish and configure daily scheduled refresh. Again, look on the internet for details. If you have credential issues, make sure they follow these settings and everything should work:</br>
![Screenshot showing credentials.](/Images/Start3.png)   
## Known Issues
1. Due to standard report features - Copilot activity on a given day, the report becomes available within 72 hours of the end of that day (in UTC) - you might notice delays even when refreshing dashboard for some values up to 3 days from the refresh time. 
2. Tables that contain users with assigned licenses take some time (unknown) to refresh. Meaning you might remove some licenses from the users, and they are still visible on the list of enabled users. How much time this takes (for them to be removed from the table) is not known to me at this point. This is relevant for the Users Page.
3. On the users page you might have situation where certain user has Last Activity Date not empty, while at the same time other cards (Teams, Chat, Outlook...) show empty values. My assumption is that these are users who use Copilot Chat (web) and they don't have M365 Copilot License assigned. Why this happens I still have no confirmation or reasoning behind it, but I will update this once either more details are provided, or Graph API is updated with Copilot Chat functions.

## Unknown Issues
1. I am not quite sure about Graph API limits to query large number of objects (if they exist). There might be some limit for data to be loaded (like I saw somewhere 10000 Entra ID entries, but I cannot confirm or deny this one) Let me know if you know.
