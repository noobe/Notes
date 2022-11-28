# Web Performance
Measuring the performance of a web application is a critical task. To understand the various bottlenecks that factor into performance of a web application, we need to understand the various steps involved in how an application loads.

Loading a resource from a web app involves the following steps:
01. User types in the url in the browser.
02. The browser checks if there is an local Domain to IP mapping for the requested url domain in system or if there is any cached info about the same.
03. If the corresponding IP is not found, the request goes to the ISP which inturn checks with multiple levels of DNS to figure it out.
04. Once the IP address is found the browser then initiates a connection request to the server system.
05. This is followed by the TLS handshake protocol to establish a secure https connection.
06. Once the connection is established, the url service request is passed to the corresponding port of the server system
07. On recieving the request, the server then process the request after checking the authentication/autherization of the requester.
08. This may involve the server making 3rd party API calls, DB connections, other data processing algorithms before a response to the request is formualated.
09. Once the server creates a response, it passes it back to the requester (client).
10. 