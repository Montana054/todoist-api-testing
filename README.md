Todoist API Testing (Postman)

Simple Postman project that demonstrates manual API testing on the Todoist Public API (v2):
auth check,
basic CRUD for tasks,
negative cases,
a short E2E chain (create → verify via API → verify in UI → delete). 
Also includes a real bug found during testing (API→UI inconsistency).


Repo structure

/collection/         # Postman collection (JSON)
/environment/        # Postman environment (JSON)
/bug-reports/        # Short written bug reports (md/pdf)
/screenshots/        # Evidence: runs, UI states, bug video/s

What’s inside
Collection: TODOIST API.postman_collection.json
Auth / Check Login (GET /projects) – basic 200/401 checks
Tasks / Create Task (POST /tasks)
Tasks / Update Task (POST /tasks/:id) – optional
Tasks / Delete Task (DELETE /tasks/:id)
E2E folder: create → check → delete (+ negative 404 on re-delete)


Environment: Todoist ENV..postman_environment.json
base_url (e.g. https://api.todoist.com/rest/v2)
token (Bearer)
task_id (set from create response)



How to run (Postman)
1. Import the collection and environment (File → Import).
2. Open Environment and set token to your Todoist API token
3. Select the environment (top‑right).
4. Run requests by folders or via Collection Runner:
E2E: expect all green; the final re-delete intentionally expects 404 (negative).




Tests & scripts
Each request has minimal tests (status, JSON shape, required fields).
Create request saves task_id to environment for chained steps.
Auth endpoint contains negative check (401 without/invalid token).

Evidence & bugs
screenshots/ — run results (green), UI screenshots, short bug video.
bug-reports/ — written reports. Key one:

SCRUM‑31: API allows creating tasks with content >500 chars; such tasks can’t be edited in UI
(API 200 vs. UI block — integration mismatch)



Notes
This repo is intentionally small and focused on manual API testing with Postman.
It’s part of a larger portfolio (UI manual, API, and UI automation).

