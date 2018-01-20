# kita
Ein python server für die Verwaltung einer Kindertagesstätte insbesondere Elterninitiativen inklusiv Social Network für die Eltern und ihre Aufgaben, und ein Rechner um das Altersstruktur nach KiBiz zu richten

## Getting Started

### System requirements for development
*   git
*   python3/pip3
*   mysql

### Set up a Dev database
Create a development database. Name it whatever you like.

    mysql -u root -p
    mysql> CREATE DATABASE kita_dev;

Create a user with a password and full access to the db.

    mysql> GRANT ALL PRIVILEGES ON kita_dev.* TO 'kita'@'localhost' IDENTIFIED BY 'dev';

Logging in to db with user to confirm success.

    mysql -u kita -p kita_dev

### Get and install the source

    git clone https://github.com/toomanydaves/kita.git
    cd kita
    pip3 install

### Create an .env file in the top-level directory to store your local credentials
    DEBUG=True
    DB_NAME='kita_dev'
    DB_USER='kita'
    DB_PASSWORD='dev'
    DB_HOST='localhost'
    DB_PORT=3306

### Migrate the db schema
    python3 manage.py migrate

### Add a superuser
    python3 manage.py createsuperuser
    
### Start the server to visit the site
    python3 manage.py runserver

## Deploy to Production
