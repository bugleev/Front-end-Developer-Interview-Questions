# Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
  > Because request is costly, so modern browsers establish 6 to 8 reusable connections to improve the download speed to prevent repeatly requsting, and because there is a limited connection count for each domain, we put resources on multiple domains.
  
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
  > - Browser look up cache, if document exists in cache and not expires, then renders it.
  
  > - OS makes DNS lookup of the IP address of given URL and replies to browser.
  
  > - If that URL exists, browser opens a TCP connection to server.
  
  > - Browser sends HTTP request to server.
  
  > - Server parses HTTP request, sends response back and may or may not close TCP connection(depends on keep-alive in header setting).
  
  > - Browser parses HTTP status code of the response and depends on what code it is to decide what to render.
  
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
  > **Long-Polling** uses setTimeout and AJAX technique to repeatedly send request and wait for server response. Before websockets, web developer used to use this technique to simulate persistent connection.

  > **Websocket** - a real persistent connection via TCP. Unlike long-polling have to setup HTTP connection with constantly requesting, once establishing websocket you don't have to send another request to maintain the connection.

  > **Server-sent** - also called server push technique. When it comes to data exchange, servers are always passive, but with server push, server can be active too. Server push is like broadcast, whoever connects to the server is a subscriber. Server push can push desired event on specific channel.

* Explain the following request and response headers:
  - Diff. between Expires, Date, Age and If-Modified-...
    > **Age**: The time in seconds the object has been in a proxy cache.
    
    > **Expires**: The date/time after which the response is considered stale.
     
    > **If-Modified-Since**: Makes the request conditional and expects the entity to be transmitted only if it has been modified after the given date. This is used to transmit data only when the cache is out of date.
      
  - Do Not Track
      > Indicates the user's tracking preference. It lets users indicate whether they would prefer privacy rather than personalized content.
    
  - Cache-Control
      >  Specify directives for caching mechanisms in both requests and responses. Caching directives are unidirectional, meaning that a given directive in a request is not implying that the same directive is to be given in the response (max-age,max-stale, min-fresh, no-cache, no-store, no-transform).
    
  - Transfer-Encoding
    > Specifies the form of encoding used to safely transfer the entity to the user. Each segment of a multi-node connection can use different Transfer-Encoding values. If you want to compress data over the whole connection, use the end-to-end Content-Encoding header instead.
  
  - ETag
    > Identifier for a specific version of a resource. It allows caches to be more efficient, and saves bandwidth, as a web server does not need to send a full response if the content has not changed. 
  
  - X-Frame-Options
    > Can be used to indicate whether or not a browser should be allowed to render a page in a `<frame>`, `<iframe>` or `<object>` . Sites can use this to avoid clickjacking attacks, by ensuring that their content is not embedded into other sites. The added security is only provided if the user accessing the document is using a browser supporting X-Frame-Options.
    
* What are HTTP methods? List all HTTP methods that you know, and explain them.
  > Create = PUT with a new URI, POST to a base URI returning a newly created URI
  
  > Read   = GET
  
  > Update = PUT with an existing URI
  
  > Delete = DELETE
