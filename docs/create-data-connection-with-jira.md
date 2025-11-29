# 2. Create the data connection with Jira

This page explains how to configure the data connection between your Q app and Jira (the runtime integration configuration and required settings).

1. Determine Jira endpoint
- Jira Cloud example: `https://your-domain.atlassian.net`
- Jira Server example: `https://jira.company.internal`

2. Choose authentication method (summary)
- OAuth 1.0a (RSA-SHA1): common for Jira Server/Data Center. Uses consumer key + RSA private key.
- OAuth 2.0 (3LO): Jira Cloud recommended for user-delegated access with scopes.
- API Token (Cloud): basic auth with email + API token (less ideal for production).

3. Configure connection values in Q app
- Environment variables (example):
  - JIRA_BASE_URL=https://your-jira-instance
  - JIRA_AUTH_METHOD=oauth1  # or oauth2, api_token
  - JIRA_CONSUMER_KEY=your-consumer-key
  - JIRA_PRIVATE_KEY_PATH=/secrets/jira_private_key.pem
  - JIRA_CLIENT_ID=...
  - JIRA_CLIENT_SECRET=...
  - JIRA_API_USER_EMAIL=...
  - JIRA_API_TOKEN=...

4. Example: making authorized REST calls
- OAuth2-acquired access_token:
  - curl -X POST "https://your-domain.atlassian.net/rest/api/3/issue" \
    -H "Authorization: Bearer <ACCESS_TOKEN>" \
    -H "Content-Type: application/json" \
    -d '{ "fields": { "project": {"key":"PROJ"}, "summary":"Test", "issuetype":{"name":"Task"} } }'

- OAuth1 (RSA) — use your Jira client library to sign requests with the private key. Example libraries: oauth-1.0a (Node), requests-oauthlib (Python with RSA support).

5. Scopes & permissions (OAuth2)
- Request scopes required for your operations:
  - For issue CRUD: `read:jira-work write:jira-work`
  - For comments or transitions: additional scopes as required.
  - Always request the least-privilege scope set.

6. Webhooks (optional)
- If you need event-driven sync (issue updates in Jira push to Q):
  - Register webhooks in Jira to point to `https://<your-app>/webhooks/jira`.
  - Verify webhook signing if available; otherwise validate requests by origin and secrets.

7. Retry & rate-limiting
- Implement retries with exponential backoff for 429/5xx responses.
- Respect Jira rate limits.

Next
- Register the Jira app and set OAuth configuration in Jira (see next doc).
