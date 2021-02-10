# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:

### 11.py
```
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
<title>11 TIMES TABLES</title>
</head>
<body style="background:black">
<center>
<h1 style="color:white"><b>11 TIMES TABLES</b><br></h1>
<h2 style="color:white">
11x0=0<br>
11x1=11<br>
11x2=22<br>
11x3=33<br>
11x4=44<br>
11x5=55<br>
11x6=66<br>
11x7=77<br>
11x8=88<br>
11x9=99<br>
11x10=110<br>
</h2>
</body>
</html>
"""

class MyHandler (BaseHTTPRequestHandler):
    def do_GET(self):
        print("request recieved")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('', 80)

httpd = HTTPServer(server_address,MyHandler)

print("my webserver is running...")

httpd.serve_forever()
```


## OUTPUT:
![output](./static/img/11.png)


## RESULT:
 Thus a simple webserver is developed to serve html pages and is hosted in the URL http://gowri.student.saveetha.in
