# UiPath Automation Project: Jira and Xero Integration

## Overview
This UiPath project automates specific tasks between Jira and Xero applications, streamlining workflows related to project management and accounting. The automation extracts task details from Jira, processes the information, and then logs time entries in Xero, ensuring accurate billing and project tracking.

## Features
- **Jira Interaction**: Extracts task details, including task IDs, descriptions, and time spent from Jira.
- **Time Entry Logging in Xero**: Logs detailed time entries in Xero based on the information extracted from Jira.
- **Dynamic Date Handling**: Utilizes system date to manage and log time entries accurately, supporting entries for *"Now"*, *"Yesterday"*, and up to *"4 Days Ago"*.
- **Error Handling**: Implements robust error handling to manage exceptions and ensure smooth workflow execution.

## Prerequisites
- UiPath Studio installed and configured.
- **`Access to Jira and Xero with necessary permissions to fetch tasks and log time entries.`**


## Workflow Detail
### Main Workflow (`Main.xaml`)
- Invokes `Jira.xaml` to extract task details from Jira.
- Receives output variables `formattedLog`, `clockValue`, and `currentDate` from `Jira.xaml`.
- Invokes `Xero.xaml` and passes the extracted details for logging time entries in Xero.

### Jira Workflow (`Jira.xaml`)
- Connects to Jira and retrieves tasks assigned within a specified timeframe.
- Formats the task details and time spent into a `formattedLog`.
- Sets `clockValue` based on the total time spent on each task.
- Outputs `formattedLog`, `clockValue`, and the date of task completion (`currentDate`).

### Xero Workflow (`Xero.xaml`)
- Receives `formattedLog`, `clockValue`, and `currentDate` from the Main workflow.
- Accesses Xero and navigates to the time entry section.
- Logs time entries using the provided details.
- Handles various UI elements in Xero to ensure accurate data entry.

## Error Handling
- Includes if conditions to manage exceptions during web interactions.
- Utilizes conditional logic to handle unexpected UI changes or data discrepancies.
- Employs logging activities to record execution details for troubleshooting.

## Setup and Execution
1. **Configuration**: Update the workflow variables with Jira and Xero access credentials and URLs.
2. **Execution**: Run the Main workflow. Monitor the execution log for any errors and ensure data is correctly processed and logged in Xero.

## Support and Contribution
- For support, raise an issue within the GitHub repository or reach out to the repository maintainers.
- Contributions are welcome. Please fork the repository, make your changes, tell me ([Vidya](https://github.com/vidyainc)) and submit a pull request for review.
