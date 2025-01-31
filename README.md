# Linkedin_Jb_search_automation
This repository contains an automated workflow designed in n8n, a low-code platform. The workflow reads filtered LinkedIn job postings via an RSS feed and updates a Google Sheet with the latest job data every time the flow is executed.

# Workflow Overview
The workflow consists of the following nodes:

# Trigger Node (When clicking Test workflow)
Google Sheets Node (appendOrUpdate_sheet)
Aggregate Node
RSS Read Node
Limit Node
Remove Duplicates Node
Google Sheets Node (appendOrUpdate_sheet)

# Detailed Explanation of Each Node
1. Trigger Node: When clicking Test workflow
Purpose: Manually trigger the workflow to execute the job search process.
How It Works: The workflow starts when the "Test Workflow" button is clicked in the n8n interface.

2. Google Sheets Node: appendOrUpdate_sheet
Purpose: Appends or updates job data in a pre-configured Google Sheet.
Functionality:
Connects to a Google Sheet via the n8n Google Sheets integration.
Data Columns in the Sheet:
Job Title
Date and Time
LinkedIn Link
Company Summary
Publish Date

3. Aggregate Node
Purpose: Aggregates and organizes job data for easier filtering and processing.
Functionality: This node consolidates the data into a format suitable for reading and updating into the Google Sheet.

4. RSS Read Node
Purpose: Fetches job postings from LinkedIn's RSS feed.
Functionality:
Reads the filtered RSS feed URL for job postings.
Extracts job data, such as the job title, description, company name, and LinkedIn link.

5. Limit Node
Purpose: Limits the number of items processed by the workflow.
Functionality: Ensures that only a set number of job postings (e.g., 25) are processed in one run.

6. Remove Duplicates Node
Purpose: Removes duplicate job entries to prevent redundancy in the Google Sheet.
Functionality:
Compares new job postings with existing entries in the Google Sheet.
Ensures that only unique job postings are added.

7. Google Sheets Node: appendOrUpdate_sheet
Purpose: Updates the Google Sheet with the filtered job data.
Functionality:
Appends new job postings to the sheet.
Updates existing entries if there are changes.

# Features
Automation: Fetches and updates job postings automatically, reducing manual effort.
Data Cleaning: Ensures no duplicate job entries are added to the Google Sheet.
Scalability: Can process a customizable number of job postings in each workflow run.
Setup Instructions
Clone this repository.
Install and configure n8n on your system or use the n8n cloud platform.
Import the workflow JSON file from this repository into your n8n instance.
Configure the RSS feed URL for LinkedIn job postings.
Link your Google account to the Google Sheets nodes.
Run the workflow and monitor the updates in your Google Sheet.

# Example Use Case
This workflow is particularly useful for job seekers or recruitment professionals who want to:

Automate the process of finding and organizing job postings.
Maintain a centralized and up-to-date database of job opportunities.
Filter jobs based on specific criteria using RSS feeds.

# Future Improvements
Add filtering for specific job roles or keywords.
Schedule the workflow to run automatically at set intervals.
Integrate additional data sources for job postings.
