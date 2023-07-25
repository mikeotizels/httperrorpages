Mikeotizels HTTP Error Pages 
============================

Version: 2.0.0 - 2022

This package contains customized error documents that can be used in palace of 
the basic HTTP error messages that the web server automatically outputs in the
event of an error.

-------------------------------------------------------------------------------

Snapshot
--------

# Included Error Pages

## Common

400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
500 Internal Server Error

## Supported

400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
405 Method Not Allowed
408 Request Timeout
410 Gone
411 Length Required
412 Precondition Failed
413 Request Entity Too Large
414 Request-URI Too Large
415 Unsupported Media Type
500 Internal Server Error
501 Not Implemented
502 Bad Gateway
503 Service Unavailable
506 Variant Also Negotiates

## Standard

- 4xx: Client Error

400 Bad Request
401 Unauthorized
402 Payment Required (Experimental)
403 Forbidden
404 Not Found
405 Method Not Allowed
406 Not Acceptable
407 Proxy Authentication Required
408 Request Timeout
409 Conflict
410 Gone
411 Length Required
412 Precondition Failed
413 Request Entity Too Large
414 Request URI Too Large
415 Unsupported Media Type
416 Requested Range Not Satisfiable
417 Expectation Failed
422 Unprocessable Content (WebDAV)
423 Locked (WebDAV)
424 Failed Dependency (WebDAV)

- 5xx: Server Error

500 Internal Server Error
501 Not Implemented
502 Bad Gateway
503 Service Unavailable
504 Gateway Timeout
505 HTTP Version Not Supported
506 Variant Also Negotiates
507 Insufficient Storage (WebDAV)
510 Not Extended

# Server Comparability Info

 - Apache HTTP Server version 2.4.x
 - LiteSpeed Web Server version 5.4.x

Modules: 

 * mod_alias 
 * mod_authz_core 
 * mod_authz_host 
 * mod_include
 * mod_negotiation

  - IIS and Nginx may be supported, but I do not know much about their modules
    and configuration.


Installation
------------

All the customized error pages named xxx.shtml (where xxx represents the HTTP 
status code, beginning in 4 or 5) should be placed in the site's web root, or
in a location of your choice. 


Configuration
-------------

# Server Configuration

## Configuration for Apache or LiteSpeed Web Server

For the web server to output the contents of the .shtml error page files, the
server web must be configured to handle .shtml files as "text/html" file types, 
process their content before sending to the client, and parse them for Server
Side Includes (SSI). Please check that the following directives are included 
and enabled in your main server configuration:

- For text/html MIME type:
  `AddType text/html .shtml`

- For server parsed files:
  `AddHandler server-parsed .shtml`

- To parse .shtml files for server-side includes (SSI):
  ("Includes" also needs to be added to the "Options" directive for per-user 
  web directories or per-VirtualHost configurations.)
  `AddOutputFilter Includes .shtml`

# Host Configuration

## Configuration for Apache or LiteSpeed Virtual Host

If the server does not automatically use any custom error page in the web root, 
or if you would like to name them differently or place them in a subdirectory 
that is relative to the site's DocumentRoot, you may also need to specify an 
ErrorDocument directive that points to the error file's location in the host's 
VirtualHost container or the site's .htaccess file. For example:

`ErrorDocument 400 /400.shtml
 ErrorDocument 401 /401.shtml
 ErrorDocument 403 /403.shtml
 ErrorDocument 404 /404.shtml
 ErrorDocument 405 /405.shtml
 ErrorDocument 408 /408.shtml
 ErrorDocument 410 /410.shtml
 ErrorDocument 411 /411.shtml
 ErrorDocument 412 /412.shtml
 ErrorDocument 413 /413.shtml
 ErrorDocument 414 /414.shtml
 ErrorDocument 415 /415.shtml
 ErrorDocument 500 /500.shtml
 ErrorDocument 501 /501.shtml
 ErrorDocument 502 /502.shtml
 ErrorDocument 503 /503.shtml
 ErrorDocument 506 /506.shtml`
 
Also note that sometimes, the personalized error page may not appear. But in 
many cases, it might be fixed by making the error page size over 1024 bytes. 

-------------------------------------------------------------------------------

Enjoy!

Michael Otieno