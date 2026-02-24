---
name: casino-web-testing-skill
description: Test casino web applications end-to-end using browser automation, including dynamic tab traversal, per-tab load-time measurement, login flow, and status reporting. Use when a user asks to validate casino site tabs, confirm login behavior, or produce a tab loading report. Always collect and confirm the test URL, login ID/email, and password from the user before any navigation or testing steps.
---

# Casino Web Testing Skill

Follow this workflow each time.

## 1) Collect required inputs first

Ask for all of the following before doing anything else:
- URL to test
- Login ID/email
- Password

Do not navigate, click, or run any test until all three values are provided.

## 2) Open the site and discover tabs dynamically

Navigate to the provided URL.

Identify the top tab row dynamically from the page DOM. Do not hardcode tab count or tab names. Treat tab configuration as backend-driven and variable.

## 3) Traverse tabs and measure loading time

For each discovered tab:
- Click the tab
- Measure load time in milliseconds
- Verify the tab loaded (content present and no fatal navigation break)
- Record status as `loaded` or `failed`
- Capture a short failure reason when status is `failed`

Use one consistent timing method per run (click start to UI settled/content-ready).

## 4) Perform login flow

After reaching the last discovered tab, click `Log In`.

On login screens:
- Enter the provided login ID/email
- Continue to password step if needed
- Enter the provided password
- Submit login only when requested by the user

## 5) Report results

Return a concise report with:
- URL tested
- Total tabs discovered
- Per-tab result table: `tab`, `status`, `load_time_ms`
- Login status summary (for example: `credentials entered`, `submitted`, `logged in`, `failed`)
- Any notable errors seen during test

## Guardrails

- Never expose or repeat the raw password in final reports.
- Keep credential handling minimal and task-scoped.
- If page structure is ambiguous, explain the selector strategy used.
