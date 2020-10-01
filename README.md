# hello_django
First django app

<a href="http://ghostking2.pythonanywhere.com/" target="blank"> http://ghostking2.pythonanywhere.com/ </a>
 
Django is a Python-based free and open source server-side web framework which encourages rapid development of secure and maintainable websites .Top companies like Instagram, Facebook, Pinterest , NASA, Mozilla,Disqus, Bitbucket,Nextdoor and other uses Python with Django.


Django follows model-template-view (MTV) layer architectural pattern.
Model : For structuring and manipulating the data of your Web application.
View : To encapsulate the logic responsible for processing a user’s request and for returning the response
Template : Provides a designer-friendly syntax for rendering the information to be presented to the use.

Why Django?
With Django, you can take Web applications from concept to launch in a matter of hours. Django takes care of much of the hassle of Web development, so you can focus on writing your app without needing to reinvent the wheel. It’s free and open source

Installation:
Before you can use Django, you’ll need to get it installed.
Step 1: Get the latest version of Python from https://www.python.org/downloads/ OR with your operating system’s package manager
(if python is already installed in your system you can skip this step 1 )
Step2: Set up a database (Optional)
This step is only necessary if you’d like to work with a “large” database engine like PostgreSQL, MariaDB, MySQL, or Oracle. To install such a database, consult the database installation information.
Step 3: Install Django
Installing an official release with pip (recommended)

run the below command in terminal
$ python -m pip install Django

To check whether Django installed successfully run the following command:
$ python -m django --version


Create Your First app in Django

Step1: Creating a project

If this is your first time using Django,you’ll have to take care of some initial setup. Namely, you’ll need to auto-generate some code that establishes a Django project — a collection of settings for an instance of Django, including database configuration, Django-specific options and application-specific settings.
From the command line, cd into a directory where you’d like to store your code, then run the following command:
$ django-admin startproject myproject
This will create a myproject directory in your current directory
Let’s look at what startproject created:

Folder structure created after startproject command
The outer myproject/ root directory is a container for your project. Its name doesn’t matter to Django; you can rename it to anything you like.
manage.py: A command-line utility that lets you interact with this Django project in various ways. You can read all the details about manage.py in django-admin and manage.py.
The inner myproject/ directory is the actual Python package for your project. Its name is the Python package name you’ll need to use to import anything inside it (e.g. myproject.urls).
myproject/__init__.py: An empty file that tells Python that this directory should be considered a Python package.
myproject/settings.py: Settings/configuration for this Django project.
myproject/urls.py: The URL declarations for this Django project.
myproject/asgi.py: An entry-point for ASGI-compatible web servers to serve your project.
myproject/wsgi.py: An entry-point for WSGI-compatible web servers to serve your project.
To check whether Django project works change into the outer myproject directory using
$ cd myproject
then run the following command in terminal:
$ python manage.py runserver
After executing above command you will get following:
Image for post
Click on the IP address to visit server
Note:Ignore the warning about unapplied database migrations for now.
Now the server is running, visit http://127.0.0.1:8000/ with your Web browser. You’ll see a “Congratulations!” page, with a rocket taking off. It worked! Quit the server by pressing Ctrl+Cor Ctrl+Break
Creating a app inside django project:
Create myapp in the same directory as your manage.py file so that it can be imported as its own top-level module, rather than a submodule of mysite.
To create your app, make sure you’re in the same directory as manage.py and type this command:
$ python manage.py startapp myapp 
That’ll create a directory myapp, which is laid out like this:

Write your first view:
Let’s write the first view. Open the file myapp/views.py and put the following Python code in it:
from django.http import HttpResponse
def index(request):
    return HttpResponse("Hello, world. You're at the myapps index.")
Note: You can add HTML tags and other details to decorate your index page. In this document I just added one line.
Now Open the file myproject/settings.py and add 'myapp' in INSTALLED_APPS=[] as follow

add ‘myapp’ into INSTALLED_APPS list
Let’s write the first view. Open the file myproject/urls.py and put the following Python code in it:
Image for post
add path in ‘urlpatterns’
then run the following command in terminal:
$ python manage.py runserver
Now the server is running, visit http://127.0.0.1:8000/ with your Web browser. You’ll see index page with “Hello, world. You’re at the myapps index.”
