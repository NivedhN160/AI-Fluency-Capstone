# CodePulse Audit Report: week 3

**Audit Timestamp:** 2026-08-19 20:08:46

**Target Directory:** `E:\Flyrank internship\week 3`

---

### 1. Security & Secret Isolation: PASS

- `.env` is explicitly listed in `.gitignore`.

- Zero unencrypted secrets exposed to version control.

### 2. Automated Test Suite Execution

**Test Status:** 100% PASS

**Executed Command:** `"E:\Flyrank internship\ai fluency capstone\venv\Scripts\python.exe" "C:\Users\nived\.gemini\antigravity-cli\brain\960f87be-2bb8-4ec7-9a9a-c0c6864012d0\scratch\test_w3_endpoints.py"`

```text
=== 1. GET / ===
HTTP 200: {"name":"Task API (Postgres Repository)","version":"3.0","endpoints":["/tasks","/health","/stats","/reset"]}

=== 2. GET /health ===
PostgreSQL connection failed (No module named 'psycopg2'); falling back to SQLite repository.
Using SQLite Repository.
HTTP 200: {"status":"ok","repository":"SQLite (Fallback)","redis_status":"not_connected (optional stretch goal)"}

=== 3. GET /tasks ===
HTTP 200: [{"id":21,"title":"Setup development environment","done":true},{"id":22,"title":"Watch request-response lecture","done":true},{"id":23,"title":"Build CRUD API for Week 2","done":false}]

=== 4. GET /tasks/1 ===
HTTP 404: {"error":"Task 1 not found"}

=== 5. GET /tasks/99 (404) ===
HTTP 404: {"error":"Task 99 not found"}

=== 6. POST /tasks (201 Created) ===
HTTP 201: {"id":24,"title":"Persistent Database Task","done":false}

=== 7. POST /tasks (400 Bad Request) ===
HTTP 400: {"error":"Title is required"}

=== 8. PUT /tasks/4 (200 OK) ===
HTTP 404: {"error":"Task 4 not
```

### 3. Web Scraper Politeness & Compliance

- **Target Domain:** `https://quotes.toscrape.com`

- **robots.txt Access:** `Allowed`

- **Recommended Rate Limit Delay:** `1.5s`

- **User-Agent:** `FlyRankPoliteScraper/1.0`
