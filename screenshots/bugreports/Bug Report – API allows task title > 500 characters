ID: API-001
Summary: API allows creation of tasks with title exceeding UI character limit (500 chars).

Preconditions:
Valid API token
Access to Todoist REST API

Steps to reproduce:
Send a POST /tasks request via API with a content field containing 501+ characters in the title.
Check the task in the UI.
Attempt to edit the same task in the UI.

Expected result:
API should return 400 Bad Request for title length > 500 characters.
Task with invalid title length should not be created in either API or UI.

Actual result:
API successfully creates a task with a title of 501+ characters (returns 200 OK).
The task is visible in UI with the full title.
When editing in UI, the Save button is disabled due to the 500-char limit.

Severity: Medium (causes inconsistent behavior between API and UI, may block editing)

Environment:
Todoist REST API v2
Postman 11.x
