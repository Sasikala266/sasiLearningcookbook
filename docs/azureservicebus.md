# azure service bus

The project depends on an active azure service bus with all the queues already configured via the Azure Portal.

Note: Remember to use free/developer/low cost azure resources when possible. Also, delete resources immediately after your coding session is done, and create them again when you begin coding again. 

1. Create a Azure Service Bus with any name.
1. Create the following queues with exact case and spelling
    1. emailshoppingcart
    1. registeruser
    1. ordercreated
    1. ordercreatedemail
1. Update 'ServiceBusConnectionString' in EmailAPI Project appsettings.json with the Connection String of the Service Bus via Shared access policies    
1. Update connectionString in 'MessageBus : IMessageBus' also with the Connection String of the Service Bus via Shared access policies
1. The Messages from the service bus are recieved and processed by the 'EmailAPI' project and store the message in the database.
    1. For example, user registraion sends a message to the registeruser and gets logged in the database
    1. The 'Email Cart' action also results in a message being logged via the queue.
    1. same happens when an order is placed.
    1. Keep checking the '[EmailLoggers]' table as new messages are processed.
1. Note: as of now, if azure service bus is not configured, the project will crash out.     

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