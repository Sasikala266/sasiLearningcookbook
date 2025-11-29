# how to run

find info about running the project locally.

## Requisites

1. All projects, except 'CBS.MessageBus' should be set as startup projects.
1. SQL Server, more notes here [sqllocal.md](sqllocal.md)
1. Azure Service Bus, more notes here [azureservicebus.md](azureservicebus.md)
1. obtain a 256 bit key, more notes here [auth.md](auth.md)
1. Obtain a Stripe key, more notes here [stripe.md](stripe.md)

## Additional Details about running this project

1. CBS.Web
   1. Nothing to Change or Update. Use as it is.
1. CBS.MessageBus
   1. Nothing to Change or Update. Use as it is.
1. CBS.EmailAPI
   1. Update 'ConnectionString'
      1. This is your SQL Server Connection String.
   1. Update 'EmailShoppingCartQueue'
      1. This is your Azure Queue for Emails
   1. Update 'RegisterUserQueue'
      1. This is your Azure Queue for User Registration
   1. Update 'OrderCreatedTopic'
      1. This is your Azure Queue for Order Creation
   1. Update 'OrderCreated_Email_Subscription'
      1. This is your Azure Queue for Email Subscription
   1. Update 'ServiceBusConnectionString'
      1. This is the connection string obtained via shared access policies
1. CBS.Services.AuthAPI
   1. Update the secret for 'Secret' with a 256 bit key
   1. Update 'ConnectionString'
      1. This is your SQL Server Connection String.
   1. Update 'RegisterUserQueue'
      1. This is your Azure Queue for User Registration
   1. Update 'ServiceBusConnectionString'
      1. This is the connection string obtained via shared access policies
1. CBS.Services.CouponAPI
   1. Update 'ConnectionString'
      1. This is your SQL Server Connection String.
   1. Update the secret for 'Secret' with a 256 bit key
   1. Update the 'SecretKey' from Stripe
1. CBS.Services.OrderAPI
   1. Update 'ConnectionString'
      1. This is your SQL Server Connection String.
   1. Update the secret for 'Secret' with a 256 bit key
   1. Update 'OrderCreatedTopic'
      1. This is your Azure Queue for Order Creation
   1. Update the 'SecretKey' from Stripe
   1. Update 'ServiceBusConnectionString'
      1. This is the connection string obtained via shared access policies
1. CBS.Services.ProductAPI
   1. Update 'ConnectionString'
      1. This is your SQL Server Connection String.
   1. Update the secret for 'Secret' with a 256 bit key
1. CBS.Services.ShoppingCarAPI
   1. Update 'ConnectionString'
      1. This is your SQL Server Connection String.
   1. Update 'EmailShoppingCartQueue'
      1. This is your Azure Queue for Emails
   1. Update the secret for 'Secret' with a 256 bit key
   1. Update 'ServiceBusConnectionString'
      1. This is the connection string obtained via shared access policies

## Video Guides

1. [https://youtu.be/ULdF8ehnjR0](https://youtu.be/ULdF8ehnjR0) : Video that shows how to download, configure and run the project locally.
1. [https://youtu.be/OPjs9nOiKjY](https://youtu.be/OPjs9nOiKjY) : Video walkthrough of the project, like a live demo.

# book a session with me

1. [calendly](https://calendly.com/jaycodingtutor/30min)

# hire and get to know me

find ways to hire me, follow me and stay in touch with me.

1. [github](https://github.com/Jay-study-nildana)
1. [personal site](https://thechalakas.com)
1. [upwork](https://www.upwork.com/fl/vijayasimhabr)
1. [fiverr](https://www.fiverr.com/jay_codeguy)
1. [codementor](https://www.codementor.io/@vijayasimhabr)
1. [stackoverflow](https://stackoverflow.com/users/5338888/jay)
1. [Jay's Coding Channel](https://www.youtube.com/channel/UCJJVulg4J7POMdX0veuacXw/)
1. [medium blog](https://medium.com/@vijayasimhabr)
