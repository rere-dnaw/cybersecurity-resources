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




## Request methods
| Method    |  Description |
|:--------------:|:-----------:|
| GET | Request a resource. It can be passed as a query URL(e.g. `?param=value`) |
| POST  | Sends data to the server. Usually used when sending login data to server. It can handle different data type. |
| HEAD | Request only header. With `curl` it's `-I` flag |
| PUT | Creates new resource on the server. |
| DELETE | Deletes new resource on the server. If not secured can lead to [[DoS]] attack. |
| OPTIONS | All information is returned in the response headers. With `curl` it's `-X OPTIONS` |
| PATCH | Add partial modifications to the resource at the specific location |
| CONNECT | The method establishes a tunnel to the server identified by the target resource. |
| TRACE | a message loop-back test along the path to the target resource. |
| PATCH | The method applies partial modifications to a resource. |


## Response Code
| Type    |  Description |
|:--------------:|:-----------:|
| 1xx | Provides info doesn't affect the request processing. |
| 2xx | Success. |
| 3xx | Client request redirected. |
| 4xx | Bad format request, request doesn't exist. |
| 5xx | Problem with HTTP server itself |

## Common codes:
| Code    | Info |  Description |
|:--------------:|:-----------:|:-----------:|
| 200 | OK | Success request |
| 301 | Moved Permanently | Redirect request e.g. `http` to `https` |
| 302 | Found | Redirect request e.g. redirect user to dashboard after login |
| 400 | Bad Request | Malformed request syntax, invalid request message framing, or deceptive request routing  |
| 403 | Forbidden | Client lack access to resource or server detect malicious input from user. |
| 404 | Not Found | Requested non existing information |
| 500 | Internal Server Error | Server can not process request |

## Accessing data through `basic HTTP authentication` (USING `GET`)
- ### `curl -u username:pass` flag
- ### web browser `username:pass@URL`
- adding authentication header when sending request e.g.  
`shell-session curl -H 'Authorization: Basic YWRtaW46YWRtaW4='`

## Accessing data through `POST` authentication:
- `curl -X POST -d 'username=admin&password=admin'`
- `curl -b 'PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1'` connect through authentication cookie
- `curl -H 'Cookie: PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1'` connect through authentication cookie passed to header


## API

### Main operation (known as CRUD APIs)
| Operation    | HTTP Method |  Description |
|:--------------:|:-----------:|:-----------:|
| Create | POST | Add row to DB |
| Read | GET | Read row from DB |
| Update | PUT | Update row in DB |
| Delete | DELETE | Delete row from DB |

### Examples:

#### Read:
```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/london | jq
```
#### Create:
```bash
curl -X POST http://<SERVER_IP>:<PORT>/api.php/city/ -d '{"city_name":"HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'
```
#### Update:
```bash
curl -X PUT http://<SERVER_IP>:<PORT>/api.php/city/london -d '{"city_name":"New_HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'
```
#### Delete:
```bash
curl -X DELETE http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City
```






#dns #http #request #/etc/hosts #fqdn #url