📌 Project Overview
This project automates the process of fetching vulnerability details from the National Vulnerability Database (NVD) API and creating incidents in ServiceNow. It ensures periodic updates by leveraging Script Includes and a Scheduled Job for proactive vulnerability management.

🚀 Features
Automated Vulnerability Retrieval – Calls the NVD API to fetch the latest vulnerabilities.

Incident Creation in ServiceNow – Parses API responses and inserts data into the Incident Table.

Scheduled Execution – Uses a Scheduled Job to run at predefined intervals.

Modular & Scalable – Implemented using Script Includes for efficient API handling.

🛠️ Technology Stack
ServiceNow (Platform)

JavaScript (Script Includes, Scheduled Jobs)

REST API (NVD API Integration)

🔧 Installation & Setup
Step 1: Create Script Includes
Navigate to System Definition → Script Includes in ServiceNow.

Create a new Script Include for handling API requests.

Mark them as Client Callable = False.

Step 2: Create a Scheduled Job
Go to System Definition → Scheduled Jobs.

Create a new Scheduled Script Execution.

Set the script to execute at a desired frequency (e.g., Daily).

Step 3: Configure the Transform Map
Navigate to System Import Sets → Transform Maps.

Create a new Transform Map named NVD_Transform_Map.

Map API response fields to corresponding Incident Table fields.

Test and activate the Transform Map.

Step 4: Test the Integration
Manually trigger the Scheduled Job.

Verify that new incidents are created in ServiceNow Incident Table with the latest vulnerability data.

🔄 Workflow Diagram
[Scheduled Job] → [Script Include Calls NVD API] → [Parses Response] → [Transform Map] → [Creates Incidents in ServiceNow]

📝 API Details
Base URL: https://services.nvd.nist.gov/rest/json/cves/2.0

Response Format: JSON

Example API Call:

request.setEndpoint("https://services.nvd.nist.gov/rest/json/cves/2.0");
request.setHttpMethod("GET");
var response = request.execute();
var responseBody = response.getBody();
📌 Future Enhancements
Implement OAuth Authentication for secure API access.

Add Email Notifications for critical vulnerabilities.

📧 Contact
For any questions, reach out to: pankajpawar5259@gmail.com
