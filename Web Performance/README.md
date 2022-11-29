# Web Performance
Measuring the performance of a web application is a critical task. To understand the various bottlenecks that factor into performance of a web application, we need to understand the various steps involved in how an application loads.

## Loading a resource from a web app involves the following steps:
01. IUser types in the url in the browser.
02. The browser checks if there is an local Domain to IP mapping for the requested url domain in system or if there is any cached info about the same.
03. If the corresponding IP is not found, the request goes to the ISP which inturn checks with multiple levels of DNS to figure it out.
04. Once the IP address is found the browser then initiates a connection request to the server system.
05. This is followed by the TLS handshake protocol to establish a secure https connection.
06. Once the connection is established, the url service request is passed to the corresponding port of the server system
07. On recieving the request, the server then process the request after checking the authentication/autherization of the requester.
08. This may involve the server making 3rd party API calls, DB connections, other data processing algorithms before a response to the request is formualated.
09. Once the server creates a response, it passes it back to the requester (client).
10. On recieving the request, probably an HTML page, the browser parses the response string and constructs a DOM and a CSSOM.
11. This is followed by the Critical Rendering Path(CRP) which involves steps like reflow and the repaint operations that finally renders the browser with the page content.

## Measuring Performance
- Web performance is typically measured in time. How long does it take for various events to happen once a user tries interact with an application through the browser.
- Events
  1. First contentful paint
  2. DOM content loaded
  3. Largest contentful paint
  4. Cumulative Layout shift

- Performance Improvements
01. File size: Since response size determines the time taken to download it to the client, reducing the file size does have a significant impact on performance

02. Non blocking download: Most HTML pages contains referances to other resources such as css, js, images, font files and setting them as deferred and asynchronous downloads makes sure that it does not block the rendering process of the reminder of the HTML page.

03. Lazy loading: Not all resources are required during the initial load of a page. For example consider a long website. The content in the bottom part of the screen would be visible to a user only when he scrolls the page down, and hence the resources such as images used below can be lazy loaded when the user navigates to that part of the page.

04. Pre connecting to other domains: Finding resources from a different domain involves the DNS convertion as well as the TLS handshake and hence preconnecting to those domains makes sure that the browser can setup a connection and be ready when a subsequent request to that domain is encountered.

05. Virtual DOM and reconciliation: Modern front end frameworks like React and VueJS maintains a virtual DOM that finds the minimal change needed to the actual DOM so that DOM updates can be kept at minimum.

06. 