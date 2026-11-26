# n8n Task Reminder Automation

## Project Description

This project was developed as part of an automation task to build a workflow that automatically checks pending tasks from Google Sheets and sends reminder emails to the employees assigned to those tasks.

The objective is to reduce manual follow-ups and ensure employees are notified about their pending responsibilities and deadlines.

## Task Requirements

The assigned task was to develop an n8n workflow with the following functionalities:

1. Schedule the workflow to run automatically every day.
2. Retrieve task records from Google Sheets.
3. Identify tasks with a `Pending` status.
4. Send reminder emails to the assigned employees using Gmail.
5. Include the task name and due date in the reminder email.

## Technologies Used

- **n8n:** Workflow automation platform.
- **Google Sheets:** Stores employee task details and task status.
- **Gmail:** Sends automated reminder notifications.

## Workflow Implementation

The workflow consists of the following nodes:

### 1. Schedule Trigger
Configured to execute the workflow automatically every day at 9:00 AM.

### 2. Get Tasks from Google Sheets
Retrieves task records from the Google Spreadsheet containing employee task information.

### 3. IF Condition – Check Task Status
Checks the status of each task.

- **True:** If the task status is `Pending`, the workflow proceeds to send an email reminder.
- **False:** If the task is completed, no reminder email is sent.

### 4. Gmail – Send Reminder Email
Sends an automated email to the assigned employee with the following information:
- Employee name
- Task name
- Due date
- Reminder message

## Google Sheets Data Structure

The Google Sheet contains the following columns:

| Column | Description |
|---|---|
| Task ID | Unique task identifier |
| Task Name | Description of the task |
| Assigned Employee | Name of the assigned employee |
| Employee Email | Employee's email address |
| Due Date | Task completion deadline |
| Task Status | Pending or Completed |

## Workflow Architecture

```text
       Schedule Trigger
        (Daily at 9 AM)
               |
               v
    Get Tasks from Google Sheets
               |
               v
       Check Task Status
               |
          +----+----+
          |         |
        TRUE       FALSE
          |         |
          v         v
     Send Reminder  Skip
       Email        Task
          |
          v
         End
```

## Sample Email Notification

**Subject:** Reminder – Complete API Documentation

Hi Rahul,

This is a reminder that your task "Complete API Documentation" is still pending.

Due Date: 26-Nov-2026

Please complete the task before the due date.

Thanks,  
Automated Task Reminder System

## Project Structure

```text
n8n-task-reminder-automation/
│
├── workflow.json
├── README.md
├── sample-data.csv
│
└── screenshots/
    ├── workflow-design.png
    ├── workflow-canvas.png
    └── successful-execution.png
```

## Execution and Testing

The workflow was configured and tested using sample task records in Google Sheets.

The testing process includes:

1. Retrieving task records from Google Sheets.
2. Verifying that the IF condition correctly identifies pending tasks.
3. Confirming that completed tasks are excluded.
4. Verifying that Gmail sends reminder emails to the assigned employees.
5. Checking that the email contains the correct task name and due date.

## Expected Outcome

- Daily automated checking of task records.
- Email reminders for pending tasks.
- Completed tasks are excluded from notifications.
- Reduced manual follow-ups.
- Improved visibility of employee task deadlines.


## Conclusion

Successfully developed an automated task reminder workflow using n8n, Google Sheets, and Gmail. The solution automates pending task identification and employee email notifications, reducing manual effort and improving task follow-up.