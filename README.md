# CSRF demo — JavaScript / Node.js

Install Node.js LTS. Open this folder in VS Code.

Run `npm install` once.

Terminal 1 (project root): `npm run main`
Open http://127.0.0.1:5000/login and sign in with student / csrf-demo.

Terminal 2 (project root): `npm run attacker`
Open http://127.0.0.1:5001/

Use 127.0.0.1 consistently; do not mix localhost and 127.0.0.1.
With mitigation DISABLED, the attacker page should change the email to changed-by-csrf@example.test.
Enable mitigation on dashboard, refresh attacker page; the GET request should return HTTP 403 and email should stay unchanged.
The legitimate POST form uses a session CSRF token.

Educational localhost-only demo. Do not deploy publicly. The session secret is a placeholder and default in-memory session storage is not production-ready.
