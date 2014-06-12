Django 1.6 on Openshift Python 2.7 gear
=======================================

This repository helps you to start running the new style Django 1.6+ on an 
Openshift python 2.7 gear

The Django project is called 'main' but feel free to change it. The default 
database is sqlite3 and is found in $OPENSHIFT_DATA_DIR/db.sqlite3 when running
in Openshift or in the projects root folder  when running locally (after calling 
'manage.py runserver')

The project has been changed as little as possible from the default. Only the 
wsgipy file that is created within the project folder has been moved to the
root folder to fit with Openshift's default behaviour

Before you push the project for the first time:
 
    1. update the entries in setup.py
    2. Update SECRET_KEY in main/settings.py
    3. get push
    4. ssh into Openshift account and then:
        cd app-root/runtime/repo
        python manage.py createsuperuser (enter admin user credentials)
        
        
On the first push the database is created but no admin user is setup, hence the
need for step 4 above.


Enjoy!
