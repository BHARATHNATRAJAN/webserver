# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```html
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',7777)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```


## OUTPUT:

### server output:
![serveroutput](https://github.com/BHARATHNATRAJAN/webserver/assets/147473529/73f98422-0714-41aa-a2c1-27a7f0865db5)


### client output:
![clientoutput](https://github.com/BHARATHNATRAJAN/webserver/assets/147473529/f157d88d-7b7e-472f-99f8-0886bd227ee5)

## RESULT:
The program is executed succesfully
