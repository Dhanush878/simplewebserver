# EX01 Developing a Simple Webserver
## Date:26.10.24

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html>
<head>
</head>
<body>
    <h1>LAPTOP CONFIGURATION</h1>
    <table border="2" cellpadding="10">
        <tr>
            <th>Property</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Device Name</td>
            <td>LAPTOP-P37ETSJO</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>AMD Ryzen 3 5300U with Radeon Graphics 2.60 GHz</td>
        </tr>
        <tr>
            <td>Installed RAM</td>
            <td>8.00 GB (7.33 GB usable)</td>
        </tr>
        <tr>
            <td>Device ID</td>
            <td>16508CEF-59BF-4873-8E6B-AE9FF5548F38</td>
        </tr>
        <tr>
            <td>Product ID</td>
            <td>00356-24755-03521-AAOEM</td>
        </tr>
        <tr>
            <td>System Type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Pen and Touch</td>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
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
httpd.serve_forever()
```

## OUTPUT:
![Screenshot 2024-10-26 001345](https://github.com/user-attachments/assets/409ffc8a-8c71-400e-8874-607d6de142f8)

![Screenshot 2024-10-26 001133](https://github.com/user-attachments/assets/60e820b3-2249-4219-9ff3-c5fc4a4bcbcb)


## RESULT:
The program for implementing simple webserver is executed successfully.
