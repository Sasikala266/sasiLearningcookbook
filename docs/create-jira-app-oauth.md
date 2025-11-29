# 3. Create the Jira app & configure OAuth permissions

This document covers the steps to register your Q application in Jira and configure OAuth so the Q app can access Jira on behalf of users.

Note: Jira Cloud and Jira Server/Data Center have different flows. Choose the one that applies.

A. Jira Cloud — OAuth 2.0 (3LO)
1. Create an OAuth 2.0 (3LO) app in Atlassian Developer Console
- Go to developer.atlassian.com/console (Atlassian developer console).
- Create a new OAuth 2.0 (3LO) app.
- Configure:
  - Name: Custom Q App
  - Authorization callback URL: `https://<your-app>/auth/callback` (or local for dev)
  - Add required scopes: e.g., `read:jira-work`, `write:jira-work`, `offline_access` (if you need refresh tokens).
- Save client ID and secret securely (JIRA_CLIENT_ID, JIRA_CLIENT_SECRET).

2. Authorization flow
- Direct users to:
  - `https://auth.atlassian.com/authorize?audience=api.atlassian.com&client_id=<CLIENT_ID>&scope=read:jira-work%20write:jira-work%20offline_access&redirect_uri=<CALLBACK_URL>&state=<STATE>&response_type=code&prompt=consent`
- Exchange authorization code for access_token at:
  - `https://auth.atlassian.com/oauth/token` (POST with client_id, client_secret, code, redirect_uri)
- Store access_token and refresh_token securely. Use refresh_token to renew tokens.

B. Jira Server / Data Center — OAuth 1.0a with RSA (common)
1. Generate RSA keypair
- Generate private key (PEM) and public key:
  - `openssl genrsa -out jira_app_privatekey.pem 2048`
  - `openssl rsa -in jira_app_privatekey.pem -pubout -out jira_app_publickey.pem`

2. Create an Application Link in Jira
- As a Jira admin, go to Jira Administration -> Applications -> Application Links.
- Enter your Q app base URL and create link.
- Edit the new Application Link and configure OAuth (incoming authentication), set:
  - Consumer Key: a unique consumer key (e.g., custom-q-app)
  - Consumer Name: friendly name
  - Public Key: paste content of jira_app_publickey.pem

3. Capture the consumer key and configure your Q app
- In your Q app configuration:
  - JIRA_AUTH_METHOD=oauth1
  - JIRA_CONSUMER_KEY=custom-q-app
  - JIRA_PRIVATE_KEY_PATH=/secrets/jira_app_privatekey.pem (store this securely)

4. User authorization
- To get an access token, you will perform the OAuth dance:
  - Request request_token from Jira OAuth endpoint.
  - Redirect the user to Jira to authorize the request_token.
  - Exchange the authorized request_token for an access token.
- Use an OAuth library that supports RSA-SHA1 signing.

Permissions & scopes (server)
- Jira Server uses application link permissions; make sure the app link is set to allow access to required resources.

C. Test the OAuth setup
- Use a REST client (curl/Postman) or your app to perform an authorized request to a simple Jira REST endpoint (GET issue).
- For example (OAuth2 bearer token):
  - curl -H "Authorization: Bearer <access_token>" "https://your-domain.atlassian.net/rest/api/3/issue/PROJ-1"

Security reminders
- Store the private key and client secrets in a secrets manager.
- Use HTTPS endpoints for callbacks and webhooks.
- Rotate secrets and support revocation if needed.

Next
- Configure the Q app to use the credentials you created and run integration tests (see next doc).
