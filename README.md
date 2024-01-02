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
```
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
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
print("webserver is running ")
httpd.serve_forever()
```
## OUTPUT:

## SERVER OUTPUT:
![Screenshot from 2024-01-02 22-12-42](https://github.com/Johnydj123/webserver/assets/145953459/d8260850-c4f0-4657-97dd-19c663e58ac3)

## CLIENT OUTPUT:
![Screenshot from 2024-01-02 22-13-30](https://github.com/Johnydj123/webserver/assets/145953459/398980aa-16a8-48a2-8822-9868e54df4de)


## RESULT:
The program is executed succesfully
