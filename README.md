# 📌 Project Overview

This project automates the process of fetching vulnerability details from the __National Vulnerability Database (NVD)__ API and creating incidents in __ServiceNow__. It ensures periodic updates by leveraging __Script Includes__ and a __Scheduled__ Job for proactive vulnerability management.



## 🚀 Features

- __Automated Vulnerability Retrieval__ – Calls the __NVD API__ to fetch the latest vulnerabilities.

- __Incident Creation in ServiceNow__  – Parses API responses and inserts data into the __Incident Table__.

- __Scheduled Execution__ – Uses a __Scheduled Job__ to run at predefined intervals.

- __Modular & Scalable__ – Implemented using __Script Includes__ for efficient API handling.

## 🛠️ Technology Stack

- __ServiceNow__ (Platform)

- __JavaScript__ (Script Includes, Scheduled Jobs)

- __REST API__ (NVD API Integration)

## 🔧 Installation & Setup

#### Step 1: Create Script Includes

1. Navigate to __System Definition__ → __Script Includes__ in ServiceNow.

2. Create a new __Script Include__ for handling API requests.

3. Mark them as __Client Callable = False__.

#### Step 2: Create a Scheduled Job

1. Go to __System Definition → Scheduled Jobs__.

2. Create a new __Scheduled Script Execution__.

3. Set the script to execute at a desired frequency (e.g., Daily).

#### Step 3: Configure the Transform Map

1. Navigate to __System Import Sets → Transform Maps__.

2. Create a new Transform Map named __NVD_Transform_Map__.

3. Map API response fields to corresponding __Incident__ Table fields.

4. Test and activate the Transform Map.

#### Step 4: Test the Integration

1. Manually trigger the Scheduled Job.

2. Verify that new __incidents__ are created in __ServiceNow Incident Table__ with the latest vulnerability data.

## 🔄 Workflow Diagram

``
[Scheduled Job] → [Script Include Calls NVD API] → [Parses Response] → [Transform Map] → [Creates Incidents in ServiceNow]
``

## 📝 API Details

- __Base URL__: ``https://services.nvd.nist.gov/rest/json/cves/2.0``

- __Response Format__: JSON

- __Example API Call__:

```var request = new sn_ws.RESTMessageV2();
request.setEndpoint("https://services.nvd.nist.gov/rest/json/cves/2.0");
request.setHttpMethod("GET");
var response = request.execute();
var responseBody = response.getBody();
```

## 📌 Future Enhancements

- Implement OAuth Authentication for secure API access.

- Add Email Notifications for critical vulnerabilities.

## 📧 Contact

For any questions, reach out to: __pankajpawar5259@gmail.com__
