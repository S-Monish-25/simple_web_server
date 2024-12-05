# EX01 Developing a Simple Webserver

# Date:18/10/2024
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from django.shortcuts import render
from http.server import BaseHTTPRequestHandler, HTTPServer
from importlib.resources import contents
from django.http import HttpResponse

content='''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>HP</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        
       body {
           font-family: 'Arial', sans-serif;
           background-color:#e7dfdf;
       }
       .container {
           width: 50%;
           margin: 0 auto;
       }
       header {
           background-color:rgb(9, 8, 8);
           color: rgb(222, 211, 211);
           padding: 10px ;
           text-align: center;
       }
       header h1 {
           font: size 3em;;
       }
       .specs {
           background-color: rgb(228, 199, 7);
           margin-top: 60px;
           border-radius: 7px;
       }
       table {
           width: 100%;
           border-collapse: collapse;
       }
       th {
           padding: 12px;
           text-align:left;
           border-bottom: 1px solid #ddd;
           background-color:rgb(10, 11, 11);
           color: white;
       }
       td {
           background-color: #f9f9f9;
           padding: 12px;
           text-align:center;
           border-bottom: 1px solid #ddd;
       }
       tr:hover {
           background-color: #f1f1f1;
       }
       footer {
           background-color:rgb(6, 6, 6);
           color: white;
           text-align: center;
           margin-top: 100px;
           padding: 1px;
       }
       </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>HP</h1>
        </header>
        
        <section class="specs">
            <table>
                <tr>
                    <th>Processor</th>
                    <td>AMD Ryzen 5 5500U </td>
                </tr>
                <tr>
                    <th>Pen and touch</th>
                    <td>No pen or touch input is available for this display</td>
                </tr>
                <tr>
                    <th>Installed ram</th>
                    <td>16.0 GB (15.3 GB usable)</td>
                </tr>
                <tr>
                    <th>Storage</th>
                    <td>512GB SSD </td>
                </tr>
                <tr>
                    <th>Graphics</th>
                    <td>Radeon Graphics</td>
                </tr>
                <tr>
                    <th>Edition</th>
                    <td>Windows 11 Home Single Language </td>
                </tr>
                <tr>
                    <th>Battery</th>
                    <td>57Wh, up to 10 hours</td>
                </tr>
                <tr>
                    <th>Weight</th>
                    <td>1.67 kg </td>
                </tr>
                <tr>
                    <th>Ports</th>
                    <td>2 x USB 3.2, 2 x USB-C, HDMI, Ethernet</td>
                </tr>
                <tr>
                    <th>Camera</th>
                    <td>1080p HD webcam</td>
                </tr>
            </table>
        </section>
        <footer>
            <p>&copy; 2024 HP. All rights reserved.</p>
        </footer>
    </div>
  
</body>
</html>'''
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address =('',8000)
Httpd = HTTPServer(server_address,Myserver)
Httpd.serve_forever()
```
# OUTPUT:

![Screenshot 2024-12-05 184010](https://github.com/user-attachments/assets/3269a4d3-ba17-4b1e-907a-9848e94554ce)
![Screenshot 2024-12-05 183946](https://github.com/user-attachments/assets/a49c695a-bb8e-42e1-b8d5-07b10bdd54db)


# RESULT:
The program for implementing simple webserver is executed successfully.
