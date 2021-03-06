### DJANGO TIPS

#### start a new project without extra project folder
    django-admin.py startproject projectname .

#### create a new app
    python ./manage.py startapp appname
    mkdir -p <appname>/templates/<appname>

#### newer migrations
    python ./manage.py makemigrations <appname>
    python ./manage.py migrate

#### test everything
    python ./manage.py test

#### test one app/module
    python ./manage.py test <appname>

#### see what sql goes with app
    python ./manage.py sqlall <appname>

#### list current dependencies (to add to requirements.txt)
    pip freeze --local

#### use django-extensions to create diagram of models
    python ./manage.py graph_models -a -o myapp_models.png

#### auto-load models into shell
    python ./manage.py shell_plus

### VIRTUAL ENVIRONMENT TIPS

#### Install a specific python version
    mkvirtualenv -p /usr/bin/python2.7 <newenvironmentname>
    mkvirtualenv -p /usr/bin/python3 <python3environment>

#### insert these into your .bashrc
    export WORKON_HOME=~/Envs
    source /usr/local/bin/virtualenvwrapper.sh

#### work within a specific environment
must be called for each shell

    workon <envname>

#### close out of a specific environment
    deactivate

#### list site packages
    lssitepackages

#### Create a new python3 venv outside virtualenvwrapper
    mkdir myproject
    cd myproject
    python3 -m venv myvenvname

#### And add these to your .bash_profile
    alias ae='deactivate &> /dev/null; source ./venv/bin/activate'
    alias de='deactivate'

#### installing packages into environment
    pip install --no-site-packages -r requirements/dev.txt
    pip install -h

#### to upgrade everything
Not sure about this thing...didn't seem to work

    pip freeze --local | grep -v '^\-e' | cut -d= -f1  | xargs pip install -U

### TEXT PROCESSING TIPS

#### replace terms within several files at once
    rpl "Original." "Replacement." fileglob
    rpl "employees" "members." *.html

#### rename portions of the file name for several files at once
    rename 's/from/to/' fileglob
    rename 's/employees/members/' module/*.html

### INSTALLING POSTGRES ON LINUX

Outside virtualenv

#### Postgresql
    sudo apt-get install postgresql postgresql-contrib
#### Find version number
    dpkg -l postgres*
#### Devel
    sudo apt-get install postgresql-server-dev-9.3
#### Debian/Ubuntu (choose based on python version)
    sudo apt-get install python-dev
    sudo apt-get install python3-dev
#### Others (choose based on python version)
    sudo apt-get install python-devel
    sudo apt-get install python3-devel

Inside virtualenv

#### Psycopg2
    pip install psycopg2

### INSTALLING POSTGRES ON MAC

    brew update
    brew upgrade
    brew install postgresql
    brew info postgresql

### POSTGRES COMMANDS
    initdb /usr/local/var/postgres -E utf8
    pg_ctl -D /usr/local/var/postgres status
    pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start
    pg_ctl -D /usr/local/var/postgres stop -s -m fast
    createuser user_name (user is alias for role with login)
    CREATE ROLE user_name WITH LOGIN;
    psql -d db_name
    psql -U postgres -c "GRANT ALL PRIVILEGES ON DATABASE db_name to user_name;"

### BUILDING AND INSTALLING PYTHON3

#### With Sqlite3
    sudo apt-get install libsqlite3.0 libsqlite3-dev
    ./configure
    make
    sudo make install

### PYTHON TIPS

#### Getting package info from within a script
    import pkg_resources
    pkg_resources.get_distribution('<package name>').version 
    pkg_resources.get_distribution('wheel').version 

### NODE TIPS
    brew update
    brew install (or upgrade) node
    npm install -g express-generator
    express newProject
    cd newProject
    npm install
    npm start

### COOL NODE LIBS
    eslint
    http-status-codes
    husky (git precommit hook)
    jasmine (tests)
    nyc (istanbul coverage checks)
    ramda (functional utilities)
    request
    rootpath (set root of path to eliminate ../../../somefile)
