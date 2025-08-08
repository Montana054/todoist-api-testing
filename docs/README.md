Todoist API Testing with Postman
This project contains my Postman collection for testing the Todoist REST API.
It covers basic CRUD operations, negative cases, and a full End-to-End flow.

📂 Project Structure
collection/      → Postman collection export (.json)
environments/    → Postman environment export (.json)
docs/            → Bug reports and testing notes
screenshots/     → Optional screenshots from UI or Runner

🚀 How to Use
Import the collection from the collection/ folder into Postman.
Import the environment from the environments/ folder.
Set your Todoist API token in the token variable (Current value).
Select the environment in Postman.
Run the requests manually or via Postman Runner:
  CRUD scenarios
  Negative scenarios
  End-to-End scenario

✨ Features
Environment variables for token, task IDs, and project IDs
Pre-request scripts for timestamps and random task content
Idempotency checks for DELETE requests
Bug reports found during testing are stored in /docs

📖 References
Todoist API Documentation
