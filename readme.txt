#######################
#Create a python environment 'myenv'
$ python3 -m venv myvenv

#######################
#To activete virtual environment
in shell: myvenv\Scripts\activate

#######################
#To create project
in shell (myenv): django-admin.exe startproject mysite .

#######################
#Settings of the site
#mysite/settings.py

STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')

ALLOWED_HOSTS = ['localhost', '127.0.0.1', '[::1]'] #['127.0.0.1', '.pythonanywhere.com']

#db settings
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}

#######################
#Create a database
#shell from djangogirls folder
python manage.py migrate

#######################
#Run web server
(myvenv) ~/djangogirls$ python manage.py runserver 0:8000

#######################
#Create an app in django
(myvenv) C:\Users\Name\djangogirls> python manage.py startapp blog

#######################
#To activate app
#mysite/settings.py

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'blog',
]

#######################
#Define Post class in 
models.py

#######################
#To update list of models
(myvenv) ~/djangogirls$ python manage.py makemigrations blog

#######################
#Apply model to the database
(myvenv) ~/djangogirls$ python manage.py migrate blog

#######################
#Register model in 
blog/admin.py

#######################
#Create user for admin.py
(myvenv) C:\Users\Name\djangogirls> python manage.py createsuperuser

#######################
#Deployment
#Install git
#Start new git repository
$ git init
Initialized empty Git repository in ~/djangogirls/.git/
$ git config --global user.name "Your Name"
$ git config --global user.email you@example.com

#Edit .gitignore and add folders, filenames and wildcart expressions to ignore.

#Adding all files (except for those that are in .gitignore) to git repository
$ git add --all .
$ git commit -m "My Django Girls app, first commit"

#Connecting local git repository to github account
$ git remote add origin https://github.com/<your-github-username>/my-first-blog.git
$ git push -u origin master

