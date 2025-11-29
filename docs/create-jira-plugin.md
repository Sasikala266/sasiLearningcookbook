# 4. [Create the Jira app & configure OAuth permissions](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/jira-actions.html)

- We already have a board created as shown in the below snippet for the testing.

![jira-board.png](images/q-app-plugin/jira-board.png)

- We need to create the plugin for the application to get the details and do the below actions on the Jira board.

![plugins_navigation.png](images/q-app-plugin/plugins_navigation.png)

    ```
       1. Read issues
       2. Create issues
       3. Search issues
       4. Change issue status
       5. Delete issue
       6. Read sprint
       7. Move issue to sprint
       8. Create sprint
       9. Delete sprint

    ```

- Click on add plugin and choose Jira cloud. Give the name to the plugin

![plugin-name.png](images/q-app-plugin/plugin-name.png)

- Pass the domain url of the Jira. To understand more about the domain url [check here](https://support.atlassian.com/jira/kb/retrieve-my-atlassian-sites-cloud-id/)

![domain-url-for-plugin.png](images/q-app-plugin/domain-url-for-plugin.png)

    ```
        Format for the domain URL should be like 

        EX: https://api.atlassian.com/ex/jira/yourInstanceId
    ```

- Pass the secret for the OAuth2.0 Authorization.

![oath-secret-for-plugin.png](images/q-app-plugin/oath-secret-for-plugin.png)

- Now pass the Access token URL, Authorization URL as shown in the below snippet.

![q-plugin-auth-access-url.png](images/q-app-plugin/q-plugin-auth-access-url.png)

- Now select the service role

![jira-service-role.png](images/q-app-plugin/jira-service-role.png)

- Now click on add plugin. It will take few moments to create the role and get the plugin ready.

![jira-plugin-created.png](images/q-app-plugin/jira-plugin-created.png)

- Now go back to the Jira assistant or launch the application if you closed it earlier using the web url.

![plugin-available-in-app.png](images/q-app-plugin/plugin-available-in-app.png)

- Let's start exploring the plugin how we can manage our Jira board. We already created the Jira board for our testing 
which is shown below.

![jira-board.png](images/q-app-plugin/jira-board.png)

### Reading the issue

- Let's ask get the details for a story or issue **Pass any key or name of your story or issue** 

![q-app-request-auth-for-jira.png](images/q-app-plugin/q-app-request-auth-for-jira.png)

- Once you asked related to the Jira Plugin for the first time , it will ask for the authorization.
- Let's click on authorize, and now you will be redirected to the new tab with all the access we are provision to the 
Jira app to access Jira from Assistant.

![provisioning-access.png](images/q-app-plugin/provisioning-access.png)

- In a couple of moments it will be back to the application, but you can see in Jira under settings--> Connected apps 
you can see the jira app got permissions to act as a handshake between Jira and Assistant.

![jira-app-access-approved.png](images/q-app-plugin/jira-app-access-approved.png)![provisioning-access.png](images/q-app-plugin/provisioning-access.png)

- Will get the results given by the assistant as shown below with the story/issue details you requested for

![result-found-for-story.png](images/q-app-plugin/result-found-for-story.png)

- We can also see the events performed by the assistant to get the details from the Jira.

![events-for-search-jira-issue.png](images/q-app-plugin/events-for-search-jira-issue.png)

- Hurray!! we got the details correctly by the assistant.

### Creating the issue

- Let's try to create an issue. Create an issue **Name of the ticket you want**

![create-jira-ticket-options.png](images/q-app-plugin/create-jira-ticket-options.png)

- Need to pass the additional information as per the need.

![view_more_fields_create_issue.png](images/q-app-plugin/view_more_fields_create_issue.png)

- It will take a couple of moments to create the Jira story/issue you requested for.

![response_for_create_jira_issue.png](images/q-app-plugin/response_for_create_jira_issue.png)

- Validate the same in the Jira board.

![issue-created-in-jira-board.png](images/q-app-plugin/issue-created-in-jira-board.png)

- We can also check the events performed by the assistant to create the story/issue from the Jira.

![events_for_create_jira_issue.png](images/q-app-plugin/events_for_create_jira_issue.png)

- Awesome!! We have done it our first Jira ticket got created.

### Delete the issue

- Let's try to delete an issue. Delete an issue **Name of the ticket/Name you want to delete**

![delete_jira_issue.png](images/q-app-plugin/delete_jira_issue.png)![create-jira-ticket-options.png](images/q-app-plugin/create-jira-ticket-options.png)

- Need to pass the additional information as per the need.
- It will take a couple of moments to delete the Jira story/issue you requested for.

![delete_jira_issue_results.png](images/q-app-plugin/delete_jira_issue_results.png)![response_for_create_jira_issue.png](images/q-app-plugin/response_for_create_jira_issue.png)

- Validate the same in the Jira board.

![deleted_jira_issue_from_board.png](images/q-app-plugin/deleted_jira_issue_from_board.png)![issue-created-in-jira-board.png](images/q-app-plugin/issue-created-in-jira-board.png)

- We can also check the events performed by the assistant to create the story/issue from the Jira.

![events_for_events_delete_issue.png](images/q-app-plugin/events_for_events_delete_issue.png)![events_for_create_jira_issue.png](images/q-app-plugin/events_for_create_jira_issue.png)

### check assignee of the issue

- Let's try to check the assignee an issue. **Who is the assignee for the Issue-123**
- It will take a couple of moments to delete the Jira story/issue you requested for.

![assignee-search-results.png](images/q-app-plugin/assignee-search-results.png)

- Validate the same in the Jira board.
- We can also check the events performed by the assistant to create the story/issue from the Jira.

![events-results-events-for-assignee.png](images/q-app-plugin/events-results-events-for-assignee.png)

