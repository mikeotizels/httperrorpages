Mikeotizels HTTP Error Pages 
============================

Version: 1.0.0 - 2021

This package contains customized error documents that can be used in palace of 
the simple hardcoded HTTP error messages that are automatically provided by the 
web server.

-------------------------------------------------------------------------------

Snapshot
--------

# Supported Error Responses

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

# Server Comparability Info

 - Apache HTTP Server 2.4.x
 - LiteSpeed Web Server 5.4.x

Modules: 

 * mod_alias 
 * mod_authz_core 
 * mod_authz_host 
 * mod_include
 * mod_negotiation


Installation
------------

All the customized error pages should be named xxx.shtml (where xxx represents 
the HTTP status code, beginning in 4 or 5) and placed in the virtual host's 
document root. 


Configuration
-------------

# Server Configuration

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

If the server does not automatically use any custom error page in the web root, 
or if you would like to name them differently or place them in a subdirectory 
that is relative to the site's DocumentRoot, you may also need to specify an 
ErrorDocument directive that points to that error file's location in the host's 
VirtualHost config block or the site's .htaccess file. For example:

ErrorDocument 400 /400.shtml
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
ErrorDocument 506 /506.shtml

-------------------------------------------------------------------------------

Enjoy!

Michael Otieno