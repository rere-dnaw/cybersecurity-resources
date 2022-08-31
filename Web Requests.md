# Web Requests:
---
## Terms:
#### FQDN - Fully Qualified Domain Name
#### URL - Uniform Resource Location

## URL structure:
URL is more than only the website which we want to visit.
![[url_structure.png]]
| Component    |  Example  |  Description |
|:--------------:|:-----------:|:------------:|
| Scheme | http:// , https://      | Identifies protocol being access from webserver        |
| User Info     | admin:pass@  | Optional user credentials parameter       |
|Host|inlanefreight.com|The host resource location|
|Port|:80|The port number for accessed service|
|Path|/dashboard.php|Points to resource being accessed.|
|Query String|?login=true|The query string starts with "?". Multiple parameters can be separated with "&"|
|Fragments|# status|Fragments are processed by the browsers on the client-side to locate sections within the primary resource (e.g. a header or section on the page).|

## HTTP Flow
![[http_flow.png]]

### **Note:** Our browsers usually first look up records in the local '`/etc/hosts`' file, and if the requested domain does not exist within it, then they would contact other DNS servers. We can use the '`/etc/hosts`' to manually add records to for DNS resolution, by adding the IP followed by the domain name.



## HTTP Request
![[web_request.png]]
| Field    |  Example  |  Description |
|:--------------:|:-----------:|:------------:|
| Method | GET | Action to perform |
| Path     | /users/login.html  | Path to resource  |
| Version | HTTP/1.1 | HTTP version |

### HTTP/1.X 
- #### requests as clear-text
- #### a new-line character to separate different fields

### HTTP/2.X
- #### dictionary requests as binary data 

## HTTP Response
![[http_response.png]]












`301 Moved Permanently`





#dns #http #request #/etc/hosts #fqdn #url