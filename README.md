# dev-tips
Just a place I stash various dev examples


###DJANGO TIPS

####start a new project without extra project folder
    django-admin.py startproject projectname .

####create a new app
    python ./manage.py startapp appname
    mkdir -p <appname>/templates/<appname>

####normal, non south, sync db
    python ./manage.py syncdb

####newer migrations
    python ./manage.py makemigrations <appname>
    python ./manage.py migrate

####test everything 
    python ./manage.py test

####test one app/module
    python ./manage.py test <appname>

####see what sql goes with app
    python ./manage.py sqlall <appname>

####list current dependencies (to add to requirements.txt)
    pip freeze --local

####use django_extensions to create diagram of models
    python ./manage.py graph_models -a -o myapp_models.png

####auto-load models into shell
    python ./manage.py shell_plus

###GIT TIPS

#### misc
    git add .
    git add filename
    git status
    git commit -m "log message"
    git commit -a -m "log message"

####push local master to origin master
-u = set the local up to track from the origin

    git push -u origin master

####short log listing
    git log --abbrev-commit --pretty=oneline

####tag releases
    git tag -a "v0.1" -m "Version 0.1"
    git push origin --tags

###VIRTUAL ENVIRONMENT TIPS

####Install a specific python version
    mkvirtualenv -p /usr/bin/python2.7 <newenvironmentname>

####work within a specific environment
must be called for each shell

    workon <envname>

####close out of a specific environment
    deactivate

####installing packages into environment
    pip install --no-site-packages -r requirements/dev.txt
    pip install -h

####to upgrade everything
Not sure about this thing...didn't seem to work

    pip freeze --local | grep -v '^\-e' | cut -d= -f1  | xargs pip install -U

###TEXT PROCESSING TIPS

####replace terms within several files at once
    rpl "Original." "Replacement." *

####rename portions of the file name for several files at once
    rename 's/from/to/' *
