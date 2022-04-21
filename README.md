# YAMDB

![Django-app workflow](https://github.com/AnnaBaziruwiha/yamdb_final/actions/workflows/yamdb_workflow.yaml/badge.svg)

### Description
This projects currently only supports Russian language.
The YaMDb project allows users to write reviews to different titles. Titles can have a genre.
Titles can be divided into categories: Books, Music, Films. The administrator can add other categories.


### Technologies
Python 3.9.0
Django 3.0.5
gunicorn 20.0.4

### Resources
**auth**: authentication

**users**: users

**titles**: items to review

**categories**: titles categories

**genres**: titles genres

**reviews**: reviews

**comments**: comments for reviews

### Deploy the project in developer mode
- Create the .env file in the root of the project and fill it with the following data:
```sh
DB_ENGINE # database
DB_NAME # database's name
POSTGRES_USER # database login
POSTGRES_PASSWORD # database password
DB_HOST # service name
DB_PORT # database port
```
- Run docker-compose in the project's directory:
```sh
docker-compose up -d
```
- Collect the project's static files in the static folder:
```sh
docker-compose exec web python manage.py collectstatic
```
- Make migrations in two stages:
```sh
docker-compose exec web python manage.py migrate auth
docker-compose exec web python manage.py migrate --run-syncdb
```
- Create a superuser:
```sh
docker-compose exec web python manage.py createsuperuser
```
- Fill the database with initial data:
```sh
docker-compose exec web python manage.py loaddata fixtures.json
```

### Contacts
Check out more of my projects [here](https://github.com/AnnaBaziruwiha)

You can send suggestions and requests to [this mail](abaziruwiha@gmail.com)

My [linkedin](https://www.linkedin.com/in/annabaziruwiha/)
