# TryHackMe — Web Application Basics

## 1. Web Application Overview

A **web application** is an application that users access through a web browser.

It mainly has two parts:

* **Front End** — Everything the user sees and interacts with.
* **Back End** — Runs on the server and handles application logic, data processing, authentication, etc.

A basic web application may require:

* **Client/Browser** — Used to access the application.
* **Web Server** — Receives and responds to requests.
* **Back-End Application** — Handles the application's logic.
* **Database** — Stores application data when required.

---

# 2. Uniform Resource Locator (URL)

A **URL (Uniform Resource Locator)** is the address used to access a resource on the internet.

It can point to:

* Webpages
* Images
* Videos
* Files
* APIs

### Example URL

```text
https://user:password@example.com:8080/products/shoes?color=black#reviews
```

## Anatomy of a URL

```text
https://user:password@example.com:8080/products/shoes?color=black#reviews
│      │             │          │    │              │           │
│      │             │          │    │              │           └── Fragment
│      │             │          │    │              └────────────── Query String
│      │             │          │    └───────────────────────────── Path
│      │             │          └─────────────────────────────────── Port
│      │             └───────────────────────────────────────────── Host / Domain
│      └─────────────────────────────────────────────────────────── User
└────────────────────────────────────────────────────────────────── Scheme
```

| Component         | Simple Explanation                                                                |
| ----------------- | --------------------------------------------------------------------------------- |
| **Scheme**        | Tells the browser which protocol to use, such as `http` or `https`.               |
| **User**          | Contains user information for authentication; rarely used in normal URLs.         |
| **Host / Domain** | Identifies the website/server you want to connect to.                             |
| **Port**          | Identifies the specific network port used by the server.                          |
| **Path**          | Tells the server which resource or location you want.                             |
| **Query String**  | Sends extra information/parameters to the server.                                 |
| **Fragment**      | Points to a specific section of a webpage and is normally handled by the browser. |

### Common Ports

```text
HTTP  → 80
HTTPS → 443
```

---

# 3. HTTP Messages

**HTTP (Hypertext Transfer Protocol)** is used for communication between a client and a web server.

There are two main types of HTTP messages:

1. **HTTP Request** — Client → Server
2. **HTTP Response** — Server → Client

```text
Client
   │
   │ HTTP Request
   ▼
Server
   │
   │ HTTP Response
   ▼
Client
```

---

# 4. HTTP Request

An **HTTP request** is sent by the client to the server to request a resource or perform an action.

An HTTP request can contain:

* Request Line
* Request Headers
* Request Body

Example:

```http
POST /login HTTP/1.1
Host: example.com
Content-Type: application/json

{"username":"nish","password":"1234"}
```

---

# 5. Request Line

The **request line** is the first line of an HTTP request.

It contains:

```text
METHOD  URL-PATH  HTTP-VERSION
```

Example:

```http
GET /products HTTP/1.1
```

## 5.1 HTTP Methods

The **HTTP method** tells the server what action the client wants to perform.

| Method      | Meaning                                                         |
| ----------- | --------------------------------------------------------------- |
| **GET**     | Retrieve data from the server.                                  |
| **POST**    | Send data to the server, usually to create or submit something. |
| **PUT**     | Replace/update an existing resource.                            |
| **PATCH**   | Partially update an existing resource.                          |
| **DELETE**  | Delete a resource.                                              |
| **HEAD**    | Similar to GET, but asks for headers without the response body. |
| **OPTIONS** | Asks the server what methods/options are supported.             |

Example:

```http
GET /products HTTP/1.1
```

This basically means:

> "Give me the `/products` resource."

---

# 6. URL Path

The **URL path** tells the server which resource or endpoint the client wants.

Example:

```http
GET /products/shoes HTTP/1.1
```

Here:

```text
/products/shoes
```

is the URL path.

It can represent:

* A webpage
* A file
* An API endpoint
* Another resource

---

# 7. HTTP Version

The **HTTP version** tells the server which version of HTTP is being used.

Example:

```http
GET /products HTTP/1.1
```

Here:

```text
HTTP/1.1
```

is the HTTP version.

Common versions:

```text
HTTP/1.0
HTTP/1.1
HTTP/2
HTTP/3
```

---

# 8. Request Headers

**Request headers** provide additional information about the request.

Format:

```text
Header-Name: Value
```

Example:

```http
Host: example.com
User-Agent: Mozilla/5.0
Accept: application/json
Content-Type: application/json
```

### Common Request Headers

| Header             | Meaning                                                       |
| ------------------ | ------------------------------------------------------------- |
| **Host**           | Tells the server which website/domain the request is for.     |
| **User-Agent**     | Provides information about the browser/client.                |
| **Accept**         | Tells the server what type of response the client prefers.    |
| **Content-Type**   | Tells the server what type of data is being sent.             |
| **Content-Length** | Tells the server the size of the request body.                |
| **Cookie**         | Sends stored cookie information to the server.                |
| **Authorization**  | Sends authentication/authorization information when required. |

---

# 9. Request Body

The **request body** contains the actual data being sent to the server.

It is commonly used with:

```text
POST
PUT
PATCH
```

Example:

```http
POST /login HTTP/1.1
Host: example.com
Content-Type: application/json

{"username":"nish","password":"1234"}
```

The following is the request body:

```json
{
  "username": "nish",
  "password": "1234"
}
```

---

# 10. Common Request Body Formats

## 10.1 JSON

**JSON (JavaScript Object Notation)** is a very common way to send structured data.

Example:

```json
{
  "username": "nish",
  "age": 19
}
```

Usually sent with:

```http
Content-Type: application/json
```

JSON stores information using **key-value pairs**.

```text
username → nish
age      → 19
```

---

## 10.2 XML

**XML (Extensible Markup Language)** uses tags to structure data.

Example:

```xml
<user>
    <username>nish</username>
    <age>19</age>
</user>
```

Usually sent with:

```http
Content-Type: application/xml
```

---

## 10.3 Form Data

**Form data** is commonly used when submitting HTML forms.

It is especially useful when the form also needs to upload files.

Example:

```text
username → nish
profile_picture → image.jpg
```

Usually sent using:

```http
Content-Type: multipart/form-data
```

---

## 10.4 URL-Encoded Data

**URL-encoded data** sends form information as key-value pairs.

Example:

```text
username=nish&age=19
```

Usually sent using:

```http
Content-Type: application/x-www-form-urlencoded
```

Special characters are encoded so they can safely be transmitted.

### Quick Difference

| Format          | Common Use                             |
| --------------- | -------------------------------------- |
| **JSON**        | APIs and structured application data   |
| **XML**         | Structured data using tags             |
| **Form Data**   | Forms, especially when uploading files |
| **URL-Encoded** | Simple HTML form data                  |

---

# 11. HTTP Response

An **HTTP response** is the message sent by the server back to the client after processing a request.

A response can contain:

* Status Line
* Response Headers
* Response Body

Example:

```http
HTTP/1.1 200 OK
Content-Type: text/html

<html>
    <body>Hello!</body>
</html>
```

---

# 12. Status Line

The **status line** is the first line of an HTTP response.

It contains three parts:

```text
HTTP-VERSION  STATUS-CODE  REASON-PHRASE
```

Example:

```http
HTTP/1.1 200 OK
```

Here:

```text
HTTP/1.1 → HTTP Version
200      → Status Code
OK       → Reason Phrase
```

---

# 13. Status Codes

An **HTTP status code** is a number that tells the client what happened to its request.

Status codes are grouped into five categories:

| Range   | Category      | Meaning                                               |
| ------- | ------------- | ----------------------------------------------------- |
| **1xx** | Informational | Request is being processed/information.               |
| **2xx** | Success       | Request was successful.                               |
| **3xx** | Redirection   | Client needs to go somewhere else or use cached data. |
| **4xx** | Client Error  | Something is wrong with the request from the client.  |
| **5xx** | Server Error  | Something went wrong on the server.                   |

---

# 14. Common Status Codes

## 200 OK

```text
200 OK
```

The request was successful.

---

## 201 Created

```text
201 Created
```

The request was successful and a new resource was created.

---

## 204 No Content

```text
204 No Content
```

The request was successful, but there is no content to return.

---

## 301 Moved Permanently

```text
301 Moved Permanently
```

The resource has permanently moved to another URL.

---

## 302 Found

```text
302 Found
```

The resource is temporarily available at another URL.

---

## 400 Bad Request

```text
400 Bad Request
```

The server could not understand or process the request because the request was invalid.

---

## 401 Unauthorized

```text
401 Unauthorized
```

Authentication is required or the provided authentication is invalid.

---

## 403 Forbidden

```text
403 Forbidden
```

The server understood the request but refuses to allow access.

---

## 404 Not Found

```text
404 Not Found
```

The requested resource could not be found.

---

## 405 Method Not Allowed

```text
405 Method Not Allowed
```

The requested HTTP method is not allowed for that resource.

Example:

```text
GET /admin
```

may be allowed, while:

```text
DELETE /admin
```

may not be allowed.

---

## 500 Internal Server Error

```text
500 Internal Server Error
```

Something went wrong on the server while processing the request.

---

## 503 Service Unavailable

```text
503 Service Unavailable
```

The server is currently unable to handle the request.

---

# 15. Reason Phrase

The **reason phrase** is the short text that appears next to the status code.

Example:

```http
HTTP/1.1 404 Not Found
```

Here:

```text
404 → Status Code
Not Found → Reason Phrase
```

It gives a human-readable description of what the status code means.

> The **status code** is what programs mainly use, while the reason phrase makes it easier for humans to understand.

---

# 16. Response Headers

**Response headers** provide additional information from the server to the client.

Example:

```http
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1024
Server: nginx
```

Some headers tell the browser:

* What type of content is being returned
* How large the response is
* How the response should be cached
* What security rules should be followed
* Information about cookies

---

# 17. Important Response Headers

## Content-Type

Tells the browser **what type of content is being returned**.

Example:

```http
Content-Type: text/html
```

This tells the browser that the response contains HTML.

Other examples:

```text
application/json
text/css
application/javascript
image/png
```

---

## Content-Length

Tells the client **how large the response body is**.

Example:

```http
Content-Length: 1024
```

---

## Location

Tells the browser **where it should go next**.

It is commonly used with redirects.

Example:

```http
HTTP/1.1 301 Moved Permanently
Location: https://example.com/new-page
```

---

## Set-Cookie

Tells the browser to **store a cookie**.

Example:

```http
Set-Cookie: sessionid=abc123
```

The browser can then send this cookie in later requests.

---

## Server

Can provide information about the **software/server handling the request**.

Example:

```http
Server: nginx
```

---

# 18. Security Headers

**Security headers** are HTTP response headers that tell the browser to follow certain security rules.

They help protect web applications against different types of attacks.

---

## 18.1 Content-Security-Policy (CSP)

```http
Content-Security-Policy: ...
```

**CSP controls which sources the browser is allowed to load content from.**

For example, it can restrict where scripts, images, styles, etc. can come from.

### Easy way to remember:

> **CSP = "Browser, only load content from places I trust."**

It can help reduce the impact of attacks such as **Cross-Site Scripting (XSS)**.

---

## 18.2 HTTP Strict Transport Security (HSTS)

```http
Strict-Transport-Security: max-age=31536000
```

HSTS tells the browser:

> **"Always use HTTPS when connecting to this website."**

This helps prevent attackers from forcing a user onto an insecure HTTP connection.

### Easy way to remember:

> **HSTS = "Always use HTTPS."**

---

## 18.3 X-Content-Type-Options

```http
X-Content-Type-Options: nosniff
```

This tells the browser **not to guess the type of a file/content**.

The browser should follow the `Content-Type` provided by the server.

### Easy way to remember:

> **nosniff = "Don't guess the content type."**

This can help prevent certain attacks where a browser incorrectly interprets a file as another type.

---

## 18.4 X-Frame-Options

```http
X-Frame-Options: DENY
```

Controls whether the webpage can be loaded inside an HTML `<iframe>`.

For example:

```text
DENY
```

means the page should not be displayed inside a frame.

This can help protect against **clickjacking**.

### Easy way to remember:

> **X-Frame-Options = "Can someone put my page inside a frame?"**

---

## 18.5 Referrer-Policy

```http
Referrer-Policy: no-referrer
```

Controls how much information about the previous webpage URL is sent when the user navigates to another page.

### Easy way to remember:

> **Referrer-Policy = "How much previous-page information should I share?"**

---

## 18.6 Permissions-Policy

```http
Permissions-Policy: geolocation=()
```

Controls which browser features the website is allowed to use.

Examples include:

* Camera
* Microphone
* Geolocation

### Easy way to remember:

> **Permissions-Policy = "Which browser features can this website use?"**

---

# 19. Request vs Response

| HTTP Request               | HTTP Response             |
| -------------------------- | ------------------------- |
| Sent by client             | Sent by server            |
| Requests a resource/action | Gives the result          |
| Contains request line      | Contains status line      |
| Contains request headers   | Contains response headers |
| May contain request body   | May contain response body |

### Basic Structure

```text
HTTP REQUEST
│
├── Request Line
│   ├── Method
│   ├── URL Path
│   └── HTTP Version
│
├── Request Headers
│
└── Request Body
```

```text
HTTP RESPONSE
│
├── Status Line
│   ├── HTTP Version
│   ├── Status Code
│   └── Reason Phrase
│
├── Response Headers
│
└── Response Body
```

---

# 20. Complete Example

### Request

```http
POST /login HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0
Accept: application/json
Content-Type: application/json

{
    "username": "nish",
    "password": "1234"
}
```

### Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 35
Strict-Transport-Security: max-age=31536000
X-Content-Type-Options: nosniff

{
    "message": "Login successful"
}
```

### Overall Flow

```text
                 HTTP REQUEST
Client ──────────────────────────────► Server
       POST /login HTTP/1.1
       Headers
       Body
                                      │
                                      │
                                      ▼
                               Server processes
                               the request
                                      │
                                      │
Client ◄────────────────────────────── Server
                 HTTP RESPONSE
                 200 OK
                 Headers
                 Body
```

### Quick Revision

```text
URL
 ↓
Identifies the resource

HTTP Request
 ↓
Client asks the server to do something

Request Line
 ↓
Method + Path + HTTP Version

Request Headers
 ↓
Extra information about the request

Request Body
 ↓
Data sent to the server

HTTP Response
 ↓
Server's reply

Status Line
 ↓
HTTP Version + Status Code + Reason Phrase

Response Headers
 ↓
Extra information about the response

Response Body
 ↓
Actual data/content returned

Security Headers
 ↓
Tell the browser to follow security rules
```


