# Ex04 Places Around Me
# name mohammed ibrahim mn
# Date: 
# AIM
To develop a website to display details about the places around my house.

# DESIGN STEPS
## STEP 1
Create a Django admin interface.

## STEP 2
Download your city map from Google.

## STEP 3
Using <map> tag name the map.

## STEP 4
Create clickable regions in the image using <area> tag.

## STEP 5
Write HTML programs for all the regions identified.

## STEP 6
Execute the programs and publish them.

# CODE
## urls.py(server1)
~~~
from django.urls import path  

from.import views  

urlpatterns=[  
    path('',views.home,name='home')  
]
~~~
## views.py(server1)  
~~~ 
from django.shortcuts import render
from http.server import BaseHTTPRequestHandler, HTTPServer
from importlib.resources import contents
from django.http import HttpResponse

content='''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>image map</title>
</head>
<body>
    <img src="Screenshot 2024-12-06 194048.png" width="1500" alt="map image" usemap="#raganadan street">
    <map name="raganadan street">
        <area shape="rect" coords="466,121,708,307" href="saravana store/saravanastore.html" target="_blank" title="CHENNAI INTERNATIONAL AIRPORT">
        <area shape="rect" coords="764,201,979,333" href="gani/gani.html" target="_blank" title="VELACHERY">
        <area shape="rect" coords="403,375,588,457" href="saravana store celebrity/saravanacelebrity.html" target="_blank" title="CHROMEPET">
        <area shape="rect" coords="144,473,371,671" href="royal foot wear/rf.html" target="_blank" title="TAMBARAM">
        <area shape="rect" coords="641,524,900,778" href="saravana store selva rathinam/saravanaselvaratinam.html" target="_blank" title="MEDAVAKKAM">
    </map>
</body>
</html>
'''
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
~~~
## urls.py(server)
~~~
from django.contrib import admin  
from django.urls import path,include  

urlpatterns = [  
    path('', include('server1.urls')),  
    path('admin/', admin.site.urls),  
]
~~~
# OUTPUT
![Screenshot 2024-12-06 204255](https://github.com/user-attachments/assets/fd62e994-7db7-41c3-b071-006695c390ca)

## IMAGE MAP IMAGE
![Screenshot 2024-12-06 204515](https://github.com/user-attachments/assets/85c2eaab-2519-42a9-82fd-4d791ce7889b)

## CHENNAI INTERNATIONAL AIRPORT
![Screenshot 2024-12-06 204538](https://github.com/user-attachments/assets/f22126c3-a0b6-4adb-9d62-a8ca4a61061c)

## VELACHERY
![Screenshot 2024-12-06 204603](https://github.com/user-attachments/assets/8ac14c78-4fd8-4e6d-88a5-00eec07b62d4)

## CHROMEPET
![Screenshot 2024-12-06 204623](https://github.com/user-attachments/assets/47c16055-1290-4028-a163-09456d148da0)

## TAMBARAM
![Screenshot 2024-12-06 204640](https://github.com/user-attachments/assets/cda636a9-e06d-410a-9407-061edbd502d5)

## MEDAVAKKAM
![Screenshot 2024-12-06 204657](https://github.com/user-attachments/assets/5524a262-3663-4c35-a1ef-5a8aedaaf31e)


# RESULT
The program for implementing image maps using HTML is executed successfully.
