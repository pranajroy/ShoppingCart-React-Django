# Shopping-cart
A simple Shopping-cart built with React and Django.

## Dependencies
* Python3+
* Node
* PostgreSQL

## Getting Started
### Installation
Create virtualenv and install all requirements in **backend** directory:

    cd shopping-cart/backend/
    python3 -m venv venv
    source venv/bin/activate
    pip install -r requirements.txt

Install all needed node_modules in **frontend** directory:

    cd shopping-cart/frontend/
    yarn install

or with npm:

    npm install

Prepare database in postgreSQL:

    sudo psql -U my_macosx_username postgres
    CREATE DATABASE shopping_cart; # Don't forget the semicolon in the end

    # Quit postgresql shell
    \q

Set up database connection in **shopping-cart/backend/backend/settings.py** in DATABASES section:

    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql_psycopg2',
            'NAME': 'shopping_cart',
            'USER': 'YOUR_USERNAME', # replace with your own username
            'PASSWORD': 'YOUR_PASSWORD', # replace with your own password
            'HOST': 'localhost',
            'PORT': ''
        }
    }

Fire up **backend** server:

    cd shopping-cart/backend/
    python manage.py migrate
    python manage.py loaddata data_dump.json
    python manage.py runserver

Open another terminal for **frontend** server:

    cd shopping-cart/frontend/
    yarn start

or with npm:

    npm start
