# HTTP-Protocol-Analysis

## Objectives

The main goal of this lab is to understand how HTTP (Hypertext Transfer Protocol) enables communication between a web client (like a browser) and a server. By analyzing HTTP packets with Wireshark, you can:

- Examine HTTP request and response headers to see what information is sent and received.

- Understand the mechanics of web communication.

- Detect potential HTTP-based attacks or data leaks, helping improve web security.

In short, it’s about learning how web traffic works and spotting security issues using packet analysis.

## Protocol Structure

HTTP Request Header: once a TCP handshake and TL SSL handshake is done, the bowser chrome or edge sends a request to for example google.com which is HTTP get message.

- GET: Requests a resource from the server.

- POST: Sends data to the server (e.g., forms, login info).

- DELETE: Removes a resource on the server.

<img width="1432" height="443" alt="image" src="https://github.com/user-attachments/assets/53c45032-b966-4564-98c7-bd6b33afbc80" />

## HTTP Status Code

If the server is readz to talk, we will a response code. A response code for example 200 which means it is perfect

<img width="868" height="279" alt="image" src="https://github.com/user-attachments/assets/3d09abf9-6dfd-4fbf-a187-3c30ae847329" />
<img width="679" height="353" alt="image" src="https://github.com/user-attachments/assets/8088a9a9-a1d1-475e-b24c-aa58d53b4bdd" />

## HTTP Request Headers

The HTTP request header is a part of the HTTP request sent by a client (like a browser) to a server. It contains metadata about the request and instructions for the server on how to handle it. Key points:

- Request Method: Specifies the type of request, e.g., GET to retrieve a resource, POST to send data.

- Host: Indicates the server’s domain name (e.g., google.com) that the client wants to communicate with.

- User-Agent: Identifies the client software, such as the browser type and version (e.g., Chrome, Edge).

- Other Headers: Can include cookies, accepted content types, language preferences, etc.

When you open your browser’s Developer Tools → Network tab → click on a request, you can see:

- The request method (GET, POST, etc.)

- The status code (like 200, which is part of the response, not the request)

- All headers sent by the browser in that request.

<img width="831" height="498" alt="image" src="https://github.com/user-attachments/assets/10da2e97-1ab3-479d-a036-5905b8acb8e6" />

After opening the Host machine web browser, I can see request headers as show below: 

<img width="835" height="802" alt="image" src="https://github.com/user-attachments/assets/70d8e199-6ab4-4669-840d-a17b9b62611c" />

## HTTP Traffics

All HTTP traffics in wireshark as at the time of the lab show below:

<img width="1084" height="664" alt="image" src="https://github.com/user-attachments/assets/6cdebcb1-aa85-444b-89e5-1f16f7dce8ec" />

## Default Port

tcp.port == 80 to show the default ports

<img width="1050" height="650" alt="image" src="https://github.com/user-attachments/assets/1ef83e85-76fe-49b1-876a-fd9aa77dbce1" />

## Get Request

http.request.method == "GET" 

<img width="1337" height="777" alt="image" src="https://github.com/user-attachments/assets/6b7a7a1d-0b53-46fe-b77a-7e2100f1ff2b" />

## View Requested Resources

http.request.uri

<img width="1196" height="677" alt="image" src="https://github.com/user-attachments/assets/9c675a9d-15cf-4db9-a800-dff2c430df82" />


## Show Cookies in HTTP Response
http.set_cookie 

<img width="1400" height="851" alt="image" src="https://github.com/user-attachments/assets/9a159bf5-fded-480b-8390-8607a5385ce1" />


## HTTP Traffic To/From Specific Host
ip.addr == 192.168.1.22 

<img width="1348" height="817" alt="image" src="https://github.com/user-attachments/assets/354be393-9515-4fea-a155-4dfa3ee334ed" />


# Conclusion

- HTTP traffic is readable and easy to analyze in Wireshark.
- Analyzing HTTP helps detect:
- Sensitive data exposure in URLs or headers
- Malware beaconing to C2 servers
- Suspicious file downloads or unauthorized access.
