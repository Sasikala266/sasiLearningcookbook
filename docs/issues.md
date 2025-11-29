# Known problems

I am tracking all issues of the current verion, and will try to fix in future version. If you find a bug, feel free to raise a issue or email me.

# issues in 1.0.0

1. Check product api app settings. Database name says, 'Database=CBS_Order'. Change that to, 'Database=CBS_Product'
1. If javascript debugging is enabled, stripe payment will trigger a breakpoint related to a 'captcha' library.
    1. As of now, I don't know why this is coming. it's not a file that I added or code that I wrote.
    1. Turn off javascript debugging in visual studio while doing stripe payment related testing. The issue does not seem to affect the payment process.
1. After placing an order, items continue to remain in the cart. 
    1. They can be manually removed, but, I need to come up with a better solution.
1. If you are not able to create the Azure Service Bus, and update the queue names,  the project will run, but, plenty of features will simply not work and the app will simply crash out.     
    1. You could update the code that depends on service in a try/catch and ask the app not to crash and skip queue messaging. 

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

