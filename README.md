API Testing Project — Todoist Public API (v2)

Overview
This project demonstrates manual and automated API testing skills using the Todoist Public API.
Focus areas: CRUD testing, negative scenarios, environment variables, and an E2E request chain.

Tools
Postman — collections, environments, test scripts
Newman — CLI execution, HTML report
Jira — bug tracking and reporting


Test Coverage
Auth check (token validation)
CRUD operations for tasks
Negative tests (invalid token, invalid payloads, exceeding limits)
E2E scenario: login → create task → update task → complete → delete
Schema validation (JSON format checks)


Deliverables
Postman collection & environment (with variables: base_url, token, task_id, …)
Newman HTML report (sample run attached)
Bug reports (Jira screenshots)
Documentation slides with summary and test design


Example Bugs Found
1. [Medium] API accepts more than 500 characters in the task name (UI limits to 500).
2. [Minor/UX] Error message not user-friendly for invalid request payload.



Project Structure
/postman
   ├── Todoist_API_Collection.json
   ├── Todoist_API_Environment.json
/reports
   ├── newman_run.html
/docs
   ├── API_Testing_Slides.pdf
   ├── BugReports_Jira.pdf



Notes
This repo is intentionally small and focused on manual API testing with Postman.
It’s part of a larger portfolio (UI manual, API, and UI automation).

