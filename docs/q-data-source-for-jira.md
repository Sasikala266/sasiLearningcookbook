# Creating the Data Source for Q as Jira:


- Once we are able to access the Q application we can create the data sources for the application.
- Click on the application from glue console and choose data source from left hand pane.

[<img src="images/q-data-source/data-source-redirect.png">]()

## Creating Index:

- If we are creating Data sources for the first time we need to create the index first.
- Click on create index , give name to the index and choose `Index provisioning` as per your use case.
- For the demo purpose we choose starter as shown in the below image.

[<img src="images/q-data-source/creating-index.png">]()

- Once the index is created you can see it in the active status as shown in the below snippet

[<img src="images/q-data-source/index-after-creation.png">]()

## Creating Data Source for Jira:

- Now we can create the data source, hit the add data source and search Jira and select.

[<img src="images/q-data-source/jira-ds-choose.png">]()

- Give Name and Description.

![ds-name-des.png](images/q-data-source/ds-name-des.png)

- Give the Jira Account URL and the Authorization 

![Jira-account-url.png](images/q-data-source/Jira-account-url.png)

- Secret with Basic auth details

![ds-secret-with-basic-auth.png](images/q-data-source/ds-secret-with-basic-auth.png)

- Secret with Oauth 2.0 details.

![scret_with_oauth_details.png](images/q-data-source/scret_with_oauth_details.png)

- Configure the VPC and Security group details as per the use case.

![data-source-vpc-details.png](images/q-data-source/data-source-vpc-details.png)

- Configure the Identity crawler and IAM role as shown in the below snippet.

![ds-iam-role.png](images/q-data-source/ds-iam-role.png)

- Choose the sync scope

![sync-scope.png](images/q-data-source/sync-scope.png)

- Choose sync Mode and Sync run schedule from the drop 

![ds-sync-mode.png](images/q-data-source/ds-sync-mode.png)

- Now choose the Field mappins for the project and Issues as per the use case.

- ![ds-mappings.png](images/q-data-source/ds-mappings.png)

- Once you click on add data source you will see a message like 

    ```
        Propagating IAM role.
        This will take 30 seconds, please remain on the page
    ```
  
- Once the data source created successfully you will get an option o sync it.

![ds-sync.png](images/q-data-source/ds-sync.png)

- Sync will take from few min to hours as per the data present.

![ds-sync-status.png](images/q-data-source/ds-sync-status.png)

- You can see the status of the sync and also the logs and report of the sync

![ds-logs.png](ds-logs.png)

- Now lets check the out Jira Assistant is fetching the details properly from the Jira data source created.
- We can observe the source is the Jira story name and the url we asked in the question to the  Jira assistant*/

![ds-test-fetching-jira-story-details.png](ds-test-fetching-jira-story-details.png)

- If we are trying fetch something not in the data source it Jira Assistant will reposnd like below

![ds-no-results-found.png.png](images/q-data-source/ds-no-results-found.png)






