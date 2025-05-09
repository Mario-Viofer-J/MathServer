# Ex.05 Design a Website for Server Side Processing
## Name: Mario Viofer J
## Reg No: 212223100032
## Date: 09/05/2025

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :

### math.html
~~~
<!DOCTYPE html>
 <html>
 <head>
 <meta charset='utf-8'>
 <meta http-equiv='X-UA-Compatible' content='IE=edge'>
 <title>Area of Surface</title>
 <meta name='viewport' content='width=device-width, initial-scale=1'>
 <style type="text/css">
 body {
    background-color: rgb(200, 255, 244);
 }
 .edge {
    width: 100%;
    padding-top: 250px;
    text-align: center;
 }
 .box {
    display: inline-block;
    border: thick dashed rgb(0, 0, 0);
    width: 500px;
    min-height: 300px;
    font-size: 20px;
    background-color:rgb(249, 208, 255);
 }
 .formelt {
    color: black;
    text-align: center;
    margin-top: 7px;
    margin-bottom: 6px;
 }
 h1 {
    color: rgb(1, 0, 33);
    padding-top: 20px;
 }
 </style>
 </head>
 <body>
 <div class="edge">
    <div class="box">
        <h1>SURFACE AREA OF RIGHT CYLINDER</h1>
        <h3>MARIO VIOFER J(212223100032)</h3>
        <form method="POST">
            {% csrf_token %}
            <div class="formelt">
                Radius: <input type="text" name="radius" value="{{r}}">m<br/
            </div>
            <div class="formelt">
                Height: <input type="text" name="height" value="{{h}}">m<br/
            </div>
            <div class="formelt">
                <input type="submit" value="Calculate"><br/>
            </div>
            <div class="formelt">
                Area: <input type="text" name="area" value="{{area}}">m<sup
            </div>
        </form>
    </div>
 </div>
 </body>
 </html>
~~~

### views.py
~~~
from django.shortcuts import render
def squarearea(request):
    context = {}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        print('request.POST:', request.POST)
        r = request.POST.get('radius', '0') 
        h = request.POST.get('height', '0') 
        print('radius =', r)
        print('height =', h)
        area = 2 * 3.14 * int(r) * int(h) + 2*3.14*int(r)*int(r)
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area =', area)
    
    return render(request, 'mathapp/math.html',context)

~~~

### urls.py
~~~
from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('squarearea/',views.squarearea,name="squarearea"),
    path('',views.squarearea,name="squarearea")
]
~~~


## SERVER SIDE PROCESSING:
![alt text](<Screenshot 2025-05-09 103922.png>)

## HOMEPAGE:
![alt text](<Screenshot 2025-05-09 103900.png>)

## RESULT:
The program for performing server side processing is completed successfully.
