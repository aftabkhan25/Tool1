Requirements
============
In order to work correctly, Tool1 needs :
+ Python 2.x where x is >= 6 (2.6, 2.7...)
+ python-requests v1.2.3 or more ( http://docs.python-requests.org/en/latest/ )
+ BeautifulSoup ( http://www.crummy.com/software/BeautifulSoup/ )
+ python-xml


How it works
============

works as a "black-box" vulnerability scanner,  that means it won't
study the source code of web applications but will work like a  fuzzer,
scanning the pages of the deployed web application, extracting links and
forms  and attacking  the scripts, sending payloads and looking for error
messages, special strings or abnormal behaviors.


General features
================

+ Generates vulnerability reports in various formats (HTML, XML, JSON, TXT...)
+ Can suspend and resume a scan or an attack
+ Can give you colors in the terminal to highlight vulnerabilities
+ Different levels of verbosity
+ Fast and easy way to activate/deactivate attack modules
+ Adding a payload can be as easy as adding a line to a text file


Browsing features
=================

+ Support HTTP and HTTPS proxies
+ Authentication via several methods : Basic, Digest, Kerberos or NTLM
+ Ability to restrain the scope of the scan (domain, folder, webpage)
+ Automatic removal of a parameter in URLs
+ Safeguards against scan endless-loops (max number of values for a parameter)
+ Possibility to set the first URLs to explore (even if not in scope)
+ Can exclude some URLs of the scan and attacks (eg: logout URL)
+ Import of cookies (get them with the wapiti-cookie and wapiti-getcookie tools)
+ Can activate / deactivate SSL certificates verification
+ Extract URLs from Flash SWF files
+ Try to extract URLs from javascript (very basic JS interpreter)
+ HTML5 aware (understand recent HTML tags)


Supported attacks
=================

+ Database Injection (PHP/ASP/JSP SQL Injections and XPath Injections)
+ Cross Site Scripting (XSS) reflected and permanent
+ File disclosure detection (local and remote include, require, fopen,
  readfile...)
+ Command Execution detection (eval(), system(), passtru()...)
+ XXE (Xml eXternal Entity) injection
+ CRLF Injection
+ Search for potentially dangerous files on the server (thanks to the Nikto db)
+ Bypass of weak htaccess configurations
+ Search for copies (backup) of scripts on the server

supports both GET and POST HTTP methods for attacks.
It also supports multipart and can inject payloads in filenames (upload).
Display a warning when an anomaly is found (for example 500 errors and timeouts)
Makes the difference  beetween permanent  and reflected  XSS vulnerabilities.


How to get the best results
===========================

To find more vulnerabilities (as some attacks are error-based), you can modify
your webserver configurations.

For example, you can set the following values in your PHP configuration :
safe_mode = Off
display_errors = On (recommended)
magic_quotes_gpc = Off
allow_url_fopen = On
mysql.trace_mode = On
