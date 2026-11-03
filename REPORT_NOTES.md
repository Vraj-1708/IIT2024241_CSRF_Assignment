# Report notes

The vulnerable GET route changes account state without a CSRF token when mitigation is disabled. The attacker page embeds that route as an image request, causing the browser to send the target site's session cookie.

The implemented mitigation checks a session flag and returns HTTP 403 before changing state when enabled. A separate legitimate POST route requires a session-bound CSRF token.

Other mitigations: avoid state-changing GET requests; use synchronizer tokens; set appropriate SameSite cookie policy; require re-authentication for sensitive actions.

Capture: initial dashboard; attacker page; successful GET change; mitigation enabled; attacker page after mitigation with 403; unchanged dashboard; legitimate protected POST success.
