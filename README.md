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
👉 [Open HTML report](./reports/newman-report.html)

##  How to Run
1. Install dependencies:
   ```bash
   npm install -g newman newman-reporter-htmlextra
2. Run collection with environment:
newman run TODOIST_API.postman_collection.json -e Todoist_ENV.postman_environment.json -r htmlextra --reporter-htmlextra-export reports/newman-report.html



Notes
Environment stores dynamic variables (task_id) between requests.
JSON Schema ensures stable response structure validation.
Negative scenarios highlight real API limitations.


