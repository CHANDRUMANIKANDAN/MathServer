# Ex.05 Design a Website for Server Side Processing
## Date:25.04.2024

## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

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
```
math.html

<html>
<head>
<title>Surface Area Of Right Cylinder</title>
<style type="text/css">
body 
{
background-color:pink;
}a
.edge {
width: 1440px;
margin-left: auto;
margin-right: auto;
padding-top: 1000px;
padding-left: 300px;
}
.box {
display:block;
border: ridge black;
width: 900px;
min-height: 500px;
font-size: 20px;
background-color:lightblue;
}
.aadhi
color:red;
text-align: center;
margin-top: 7px;
margin-bottom: 6px;
}
h1
{
color:black;
text-align: center;
padding-top: 20px;
}
</style>
</head>
<body>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
<div class="edge" align="center">
<div class="box">
<h1>Surface Area Of A Right Cylinder</h1>
<h2> Aadithya.R  212223240001</h2>
<br>
<br>
<form method="POST">
{% csrf_token %}
<div class="aadhi">
Radius : <input type="text" name="Radius" value="{{r}}"></input>(in m)<br/>
<br>
</div>
<div class="aadhi">
Height: <input type="text" name="Height" value="{{h}}"></input>(in m)<br/>
<br>
</div>
<div class="aadhi">
<input type="submit" value="Calculate"></input><br/>
<br>
</div>
<div class="aadhi">
Area : <input type="text" name="area" value="{{area}}"></input>m<sup>2</sup><br/>
</div>
</form>
</div>
</div>
</body>
</html>



views.py

from django.shortcuts import render
def surfacearea(request):
    context={}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        r = request.POST.get('Radius','0')
        h = request.POST.get('Height','0')
        print('request=',request)
        print('Radius=',r)
        print('Height=',h)
        area = (2*3.14*int(r)*int(h)+(2*3.14*int(r)*int(r)))
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area=',area)
    return render(request,'amira/math.html',context)



urls.py

from django.contrib import admin
from django.urls import path
from amira import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('surfaceareaofrighttcylinder/',views.surfacearea,name="surafceareaofrightcylinder"),
    path('',views.surfacearea,name="surafceareaofrightcylinderroot")
]

```



## SERVER SIDE PROCESSING:


![image](https://github.com/CHANDRUMANIKANDAN/MathServer/assets/118644502/8db83a4f-80b9-497a-825a-230fd9882a3f)

## HOMEPAGE:

![image](https://github.com/CHANDRUMANIKANDAN/MathServer/assets/118644502/459e2bbb-c0bf-4601-a3b8-2434f48bca1b)


## RESULT:
The program for performing server side processing is completed successfully.
