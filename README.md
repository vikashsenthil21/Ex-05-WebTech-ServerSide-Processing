# Design a Website for Server Side Processing

# AIM:

To design a website to perform mathematical calculations in server side.

# DESIGN STEPS:

## Step 1:

Crete new Project And App in Django.

## Step 2:

Type the code in views and urls files




## Step 3:

Create the Html files


## Step 4:

Run The server



## Step 5:

The website in the URL.http://vikashsenthil.student.saveetha.in:8000/volume/



# PROGRAM:
```
<!DOCTYPE html>
<html>
    <head>
        <title>
            www.volume.html
        </title>
    </head>
<style>
    *{
        box-sizing: border-box;
         }

    body{
    background-color;
    color: black;
    }

   .container{
    width: 1080px;
    height: 350px;
    margin-top: 100px;
    margin-left: auto;
    margin-right: auto;
    border-radius: 25px;
    border: 10px solid black;
    
    
    }
    h1{
        color: rgb(0, 0, 0);
        text-align: center;
    }
    .calculate{
        padding-top: 10px;
        padding-bottom: 10px;
        padding-left: 10px;
        padding-right:10px;
        text-align: center;
        font-size: 20px;
        padding-top: 7px;
        font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    }
</style>
    <body>
        <div class="container">
        <h1>TO CALCULATE VOLUME</h1>
        <form method="POST">
            {% csrf_token %}
            <div class="calculate"> 
                Height:<input type="text" name="height" value={{h}}></input><br/>
            </div>
            <div class="calculate">
                Length:<input type="text" name="length" value={{l}}></input><br/>
            </div>
            <div class="calculate">
                Width:<input type="text" name="width" value={{w}}></input><br/>
            </div>
            <div class="calculate">
                <input type="submit" value="Calculate Volume"></input><br/>
            </div>
          
         <div class="calculate">
                Volume:<input type="text" name="volume" value={{volume}}></input>
            </div>
        </form>
    </div>
    </body>
</html>

```
VIEWS.PY:

```
from django.shortcuts import render
def home(request):
    context = {}
    context["a"] = ''
    context["b"] = ''
    context["c"] = ''
    if request.method == 'POST':
        a = request.POST.get('ADJACENT', '')
        b = request.POST.get('OPPOSITE', '')

        c=int(a)**2+int(b)**2
        context['c'] = c
        context['a'] = a
        context['b'] =b

    return render(request, "cal/home.html", context)
```
URLS.PY:

```
from django.urls import path
from cal import views
urlpatterns = [
 path('admin/', admin.site.urls),
 path('home/',views.home,name="home"),
 path('',views.home ,name="cal")
]

```

# OUTPUT:


![WhatsApp Image 2023-01-29 at 15 18 43](https://user-images.githubusercontent.com/119433834/215319950-0008d644-4585-40d9-bf5c-a17f38bc130a.jpg)


# RESULT:


The program is executed succesfully
