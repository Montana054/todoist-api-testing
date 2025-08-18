#  Todoist API Testing (Postman + Newman)

##  Purpose
Demonstrate API testing skills using **Postman** and **Newman** on the [Todoist Public API v2](https://developer.todoist.com/rest/v2/).

##  Tools & Technologies
- Postman (requests & test scripts)  
- Collection & Environment variables (`base_url`, `token`, `task_id`, etc.)  
- JSON Schema validation  
- Negative testing & E2E scenarios  
- Newman + HTML reports  

##  Coverage
- **Auth check** – validate token, status codes, response schema  
- **CRUD for tasks**  
  - `POST /tasks` – create task  
  - `GET /tasks/:id` – fetch by ID  
  - `DELETE /tasks/:id` – delete task  
  - `GET /tasks` – check task list  
- **Negative cases** – invalid token, deleted task by ID  
- **E2E chain** – create → get by id → delete → verify absence  

## Example Newman Report
👉 [Open HTML report]([file:///C:/Users/user/Downloads/todoist_e2e-report.html](https://github.com/Montana054/todoist-api-testing/tree/912058cf7514c543d661d57090597ef69d91de4d/newman%20reports))

##  How to Run
1. Install dependencies:
   ```bash
   npm install -g newman newman-reporter-htmlextra
2. Run collection with environment:
newman run TODOIST_API.postman_collection.json -e Todoist_ENV.postman_environment.json -r htmlextra --reporter-htmlextra-export reports/newman-report.html

## Evidence & bugs
screenshots/ — run results (green), UI screenshots, short bug video.
bug-reports/ — written reports. Key one:
SCRUM‑31: API allows creating tasks with content >500 chars; such tasks can’t be edited in UI
(API 200 vs. UI block — integration mismatch)


## Implamantation Retails
Environment stores dynamic variables (task_id) between requests.
JSON Schema ensures stable response structure validation.
Negative scenarios highlight real API limitations.


## Notes
This repo is intentionally small and focused on manual API testing with Postman.
It’s part of a larger portfolio (UI manual, API, and UI automation).
