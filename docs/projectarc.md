# Project Architecture
[<img src="cbsb.png">]()

Welcome to the project architecture notes. 

The primary purpose of the project is do the usual .net micro services approach which makes in the context. I have a basic e-commerce project going on here. The app is to do the following.

1. authentication and authorization service/api
1. basic e-commerce operations
    1. product management service/api
        1. customer should be able to look at products
        1. admin should be able to add and edit products
    1. order management service/api
        1. customer places orders
        1. admin manages it
    1. coupon management service/api
        1. customer uses coupons during checkout
        1. admin manages coupons
    1. shopping cart management service/api
        1. customer adds and removes products from the cart
1. message bus and email processor/logger
    1. Collect messages from different services and put it in the Azure queue
    1. Receive messages from the Azure Queue, and process it (like log the database to the database. in the future, may be, send email and such)
1. Provide a web app that gives a UI to do all the above
    1. customer does customer things
    1. admin does admin things

Now, each component is developed as a separate project, either as a web api, or a web app or a class project. That means, each of them can be individually developed, debugged and deployed. This leads to some duplication (like DTO classes for example), but, it's a small price to pay for the flexibility offered by the micro service approach.     

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