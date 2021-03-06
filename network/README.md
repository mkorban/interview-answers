# Network Q&As

## Traditionally, why has it been better to serve site assets from multiple domains?

Web browsers are restricted to download several items per host at once, 
so the more resources hosted on external domains you use the faster a page loads.
Old IEs permitted only 2 request, modern browsers allow 6 — 8 requests, 
but there are still reasons to use this aproach.

If your server’s domain set a cookie on the client, 
that client will send the cookie on every request it makes to your domain, 
including those requests for static assets.

But each new domain you reference has the upfront cost of a DNS lookup, 
so you have to be sure that it’s actually going to be worth it. 
If you are a small site then serving assets from a subdomain will likely not be worth it;
the browser can probably fetch several under-parallelised assets from one domain quicker 
than it can perform DNS lookups across multiple domains and parallelise those.
You can still use `dns-prefetch` though.

## What is Hyper Text Transfer Protocol

Hypertext Transfer Protocol (HTTP) is a networking protocol for distributed, collaborative, hypermedia information systems. HTTP is the foundation of data communication for the World Wide Web.

## What is HTTP session?

HTTP session is a sequence of network request-response transactions. An HTTP client initiates a request. It establishes a Transmission Control Protocol (TCP) connection to a particular port on a host (typically port 80; see List of TCP and UDP port numbers). An HTTP server listening on that port waits for a client's request message. Upon receiving the request, the server sends back a status line, such as "HTTP/1.1 200 OK", and a message of its own, the body of which is perhaps the requested resource, an error message, or some other information.
