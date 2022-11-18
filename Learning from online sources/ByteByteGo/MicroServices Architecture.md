# What Are Microservices Really All About? (And When Not To Use It)
Source: https://www.youtube.com/watch?v=lTAcCNbJ7KE

Notes:
- Microservices architecture enables large teams to build scalable applications that are composed of many loosely coupled services.
- Each loosely coupled service in the architecutre take care of a dedicated function inside a large scale application.
- Eg: In a online shopping site: Shopping Cart | Billing | User Profile | Push Notifications
can all be handled by individual services.
- These functional areas are sometimes called Domains.
- As seen above most flows involve passing from one micro service functionality to the other and hence they need to communicate. This is done through well defined interfaces with small service areas.
- The small surface areas limits the blast area radius of failures and defects making it each service easier to reason about in the context of the full flow or application. This makes it easier to pin point a failure and its root cause.
- Microservices can be independently deployed.
- Since each service is small, easier to reasong about and has a smaller blast radius - this gives the team peace of mind and confidence to deploy often.
- These communication interfaces used to communicate comprices of:
    Remote Procedure Calls or RPCs
    Event Streaming
    Message Brockers

- RPC like gRPC provides faster respone suring communication but the blast radius or its impact to other services would be larger when a service goes down.
- Event Streaming provides better isolation to services but they take longer to process

- Microservices Architecture is costlier to create and maintain.