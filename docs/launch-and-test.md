# 4. Launch the Q application and test Jira access (create, update, delete)

This page shows how to start your Q app locally (or in the target environment) and test Jira operations.

1. Prepare environment
- Ensure required env vars/secrets are set:
  - JIRA_BASE_URL
  - JIRA_AUTH_METHOD
  - JIRA_CLIENT_ID / JIRA_CLIENT_SECRET (if oauth2)
  - JIRA_CONSUMER_KEY / JIRA_PRIVATE_KEY_PATH (if oauth1)
  - CALLBACK_URL
- For local testing, run:
  - export JIRA_BASE_URL="https://your-domain.atlassian.net"
  - export JIRA_AUTH_METHOD="oauth2"
  - export JIRA_CLIENT_ID="..."
  - export JIRA_CLIENT_SECRET="..."
  - export CALLBACK_URL="http://localhost:3000/auth/callback"

2. Start the application
- Example Node.js:
  - npm install
  - npm run dev
- Make sure the server listens on the configured CALLBACK_URL and has routes:
  - /auth/start  (to begin OAuth flow)
  - /auth/callback (to receive authorization code)
  - /api/jira/create-issue
  - /api/jira/update-issue
  - /api/jira/delete-issue

3. Test create (example)
- Using your app’s proxy endpoint that calls Jira (recommended to ensure the app auth logic is working):
  - curl -X POST http://localhost:3000/api/jira/create-issue \
    -H "Content-Type: application/json" \
    -d '{"projectKey":"PROJ","summary":"Test issue from Q app","description":"Created via integration","issueType":"Task"}'

- Alternatively directly to Jira (if you have a valid access token):
  - curl -X POST "https://your-domain.atlassian.net/rest/api/3/issue" \
    -H "Authorization: Bearer <ACCESS_TOKEN>" \
    -H "Content-Type: application/json" \
    -d '{"fields":{"project":{"key":"PROJ"},"summary":"Test issue","issuetype":{"name":"Task"}}}'

4. Test update
- Update summary or fields:
  - curl -X PUT "https://your-domain.atlassian.net/rest/api/3/issue/PROJ-123" \
    -H "Authorization: Bearer <ACCESS_TOKEN>" \
    -H "Content-Type: application/json" \
    -d '{"fields":{"summary":"Updated summary from Q app"}}'

5. Test delete
- Delete an issue (note: depending on your workflow you may prefer to transition to Done instead of deleting):
  - curl -X DELETE "https://your-domain.atlassian.net/rest/api/3/issue/PROJ-123" \
    -H "Authorization: Bearer <ACCESS_TOKEN>"

6. Verify results
- Confirm in Jira UI that the issue was created, updated, or deleted.
- Check your app logs for success/failure responses from Jira. Log request IDs from Jira for troubleshooting.

7. Automated tests (recommended)
- Write unit tests / integration tests that:
  - Mock Jira responses for CI.
  - Run real end-to-end tests in a staging environment with a test Jira site.

Troubleshooting
- 401 Unauthorized: check token, client credentials, callback URL, or app link configuration.
- 403 Forbidden: insufficient permissions / scopes.
- 429 Too Many Requests: implement backoff and respect rate limits.
- 500/502/503: transient server error — retry.

Next
- After verification, deploy the app to your production environment, ensure secrets are set, and monitor logs and Jira API usage.
