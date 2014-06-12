Django 1.6 on Openshift Python 2.7 gear
=======================================

This repository helps you to start running the new style Django 1.6+ on an 
Openshift python 2.7 gear

The Django project is called `main` but feel free to change it. The default 
database is sqlite3 and is found in `$OPENSHIFT_DATA_DIR/db.sqlite3` when
running in Openshift or in the projects root folder  when running locally 
with Django's test server

The project has been changed as little as possible from the default. Only the 
`main/wsgi.py` file that is created within the project folder has been moved 
to the root folder to fit with Openshift's default behaviour

The easiest way to use this template is to create a Openshift project using the 
web site. Choose the Python 2.7 cartridge, then on the setting page enter your
chosen project name. In the "Source Code" input box enter the dhango-on-openshift
https link (https://github.com/ptav/django-on-openshift.git). Chose your 
preferred scaling option and click he "Create Application" button. Once finished 
you can clone the project locally.

Before you push the project for the first time:
 
  1.  Update `setup.py`
  2.  Update `SECRET_KEY` in `main/settings.py`
  3.  `git push`
  4.  ssh into Openshift account and then:
        `cd app-root/runtime/repo`
        `python manage.py createsuperuser` (enter admin user credentials)
        

On the first push the database is created but no admin user is setup, hence the
need for step 4 above.


Enjoy!
