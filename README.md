# EX01 Developing a Simple Webserver
## Date:28.09.2026

## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <title>LAPTOP STORE</title>
    </head>
    <body style="color : white" bgcolor="black">
        <h1>NIKSHITHA M 26009747</h1>
        <table border="1">
            <tr>
                <th>1</th>
                <th>Device name</th>
                <th>TL15-53M-G2</th>
            </tr>
            <tr>
                <th>2</th>
                <th>Processor</th>
                <th>Intel(R) Core(TM) 5 210H (2.20 GHz)</th>
            </tr>
            <tr>
                <th>3</th>
                <th>Installed RAM</th>
                <th>16.0 GB (15.7 GB usable)</th>
            </tr>
            <tr>
                <th>4</th>
                <th>Graphics card</th>
                <th>Intel(R) Graphics (128 MB)</th>
            </tr>
            <tr>
                <th>5</th>
                <th>Storage</th>
                <th>117 GB of 477 GB used</th>
            </tr>
            <tr>
                <th>6</th>
                <th>Device ID</th>
                <th>E53B61F1-CDC2-413C-81B2-7261BFC7A4F7</th>
            </tr>
            <tr>
                <th>7</th>
                <th>Product ID</th>
                <th>00342-42954-11486-AAOEM</th>
            </tr>
            <tr>
                <th>8</th>
                <th>System type</th>
                <th>64-bit operating system, x64-based processor</th>
            </tr>
            <tr>
                <th>9</th>
                <th>Pen and touch</th>
                <th>No pen or touch input is available for this display</th>
            </tr>
        </table>
    </body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Client request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my own webserver is running successfully...")
httpd.serve_forever()
```

## OUTPUT:
webpage
![alt text](<Screenshot (20).png>)
webserver
![alt text](<Screenshot (21).png>)
## RESULT:
The program for implementing simple webserver is executed successfully.
