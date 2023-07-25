HTTP Error Pages 
================

In this repository, you may find customized HTTP error documents that can be 
used in place of the web server's simple hardcoded error responses an existing 
default error document configured in the main server's configuration file.

# Overview

An error page informs a visitor when there is a problem accessing your website. 
Each type of problem has its own status code. For example, a visitor who enters
a nonexistent URL will see a 404 error, while an unauthorized visitor trying to 
access a restricted area of your site will see a 401 error.

Basic HTTP error messages are automatically provided by the web server, however,
these generic error responses may be less uninformative and can be intimidating 
to some visitors. You may wish to display custom error messages which are either 
friendlier, or in some language other than English, or perhaps which are styled 
more in line with your site layout.

Customized error messages can be defined for any HTTP status code designated as 
an HTTP error condition, beginning in 4 or 5. Additionally, some useful server 
environment variables can be used (if available) to further customize the error 
documents based on the values of these variables.

-------------------------------------------------------------------------------

# HTTP Error Codes

## Common HTTP Error Codes

  - 400 Bad Request
  - 401 Unauthorized
  - 403 Forbidden
  - 404 Not Found
  - 500 Internal Server Error

## Standard HTTP Error Codes

Below are the standard HTTP error status codes as defined by [RFC 9110][1]. 

4xx: Client Error
-----------------

  - 400 Bad Request
  - 401 Unauthorized
  - 402 Payment Required (Experimental)
  - 403 Forbidden
  - 404 Not Found
  - 405 Method Not Allowed
  - 406 Not Acceptable
  - 407 Proxy Authentication Required
  - 408 Request Timeout
  - 409 Conflict
  - 410 Gone
  - 411 Length Required
  - 412 Precondition Failed
  - 413 Request Entity Too Large
  - 414 Request-URI Too Large
  - 415 Unsupported Media Type
  - 416 Requested Range Not Satisfiable
  - 417 Expectation Failed
  - 418 I'm a teapot
  - 421 Misdirected Request
  - 422 Unprocessable Content - [WebDAV][2]
  - 423 Locked - [WebDAV][2]
  - 424 Failed Dependency - [WebDAV][2]
  - 425 Too Early (Experimental)
  - 426 Upgrade Required
  - 428 Precondition Required
  - 429 Too Many Requests
  - 431 Request Header Fields Too Large
  - 451 Unavailable For Legal Reasons

5xx: Server Error
-----------------

  - 500 Internal Server Error
  - 501 Not Implemented
  - 502 Bad Gateway
  - 503 Service Unavailable
  - 504 Gateway Timeout
  - 505 HTTP Version Not Supported
  - 506 Variant Also Negotiates
  - 507 Insufficient Storage - [WebDAV][2]
  - 508 Loop Detected - [WebDAV][2]
  - 510 Not Extended
  - 511 Network Authentication Required

  [1]: https://httpwg.org/specs/rfc9110.html#overview.of.status.codes
  [2]: https://developer.mozilla.org/en-US/docs/Glossary/WebDAV

NOTE:

If you receive a response that is not in the list above, it is a non-standard 
status code, possibly custom to the server's software. 

Also, note that some error codes listed above may have different descriptions on 
different web server products or the underlying web applications, for example:

 * 413 Content Too Large|Payload Too Large|Request Entity Too Large
 * 414 URI Too Long|Request URI Too Long
 * 414 Range Not Satisfiable|Requested Range Not Satisfiable
 * 422 Unprocessable Content|Unprocessable Entity

-------------------------------------------------------------------------------

# References

## General

 * @see http://tools.ietf.org/html/rfc7231#section-6
 * @see https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml
 * @see https://httpstatuses.com

## Specific

 * [102 Processing] (http://www.iana.org/go/rfc2518)
 * [103 Early Hints] (http://www.ietf.org/rfc/rfc8297.txt)
 * [207 Multi-Statu] (http://www.iana.org/go/rfc4918)
 * [208 Already Reporte] (http://www.iana.org/go/rfc5842)
 * [226 IM Use] (http://www.ietf.org/rfc/rfc3229.txt)
 * [308 Permanent Redirect] (http://www.ietf.org/rfc/rfc7238.txt)
 * [418 I'm a teapot] (http://www.ietf.org/rfc/rfc2324.txt)
 * [421 Misdirected Request] (http://www.iana.org/go/rfc7540) Section 9.1.2
 * [422 Unprocessable Entity] (http://www.iana.org/go/rfc4918)
 * [423 Locked] (http://www.iana.org/go/rfc4918)
 * [424 Failed Dependency] (http://www.iana.org/go/rfc4918)
 * [425 Too Early] (https://datatracker.ietf.org/doc/draft-ietf-httpbis-replay)
 * [428 Precondition Required] (http://www.ietf.org/rfc/rfc6585.txt)
 * [429 Too Many Requests] (http://www.ietf.org/rfc/rfc6585.txt)
 * [431 Request Header Fields Too Large] (http://www.ietf.org/rfc/rfc6585.txt)
 * [451 Unavailable For Legal Reasons] (http://tools.ietf.org/html/rfc7725)
 * [506 Variant Also Negotiates] (http://www.ietf.org/rfc/rfc2295.txt)
 * [507 Insufficient Storage] (http://www.iana.org/go/rfc4918)
 * [508 Loop Detected] (http://www.iana.org/go/rfc5842)
 * [510 Not Extended] (http://www.ietf.org/rfc/rfc2774.txt)
 * [511 Network Authentication Required] (http://www.ietf.org/rfc/rfc6585.txt)
 * [499 Client Closed Request] (http://lxr.nginx.org/source/src/http/ngx_http_request.h#0133)
 * [599 Network Connect Timeout Error] (https://httpstatuses.com/599)
