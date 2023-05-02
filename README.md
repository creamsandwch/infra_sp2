# YaMDb
### The YaMDb project collects users feedback on products. The products themselves are not stored in YaMDb; you cannot watch a movie or listen to music here.
___
### Grateful or indignant users leave text reviews for the products and rate the product in the range from one to ten; from user ratings, an average rating of the product is formed. A user can leave only one review per work.
___

### REST API Django project in a Docker container.
___

## Launch
To launch web application it is needed to build a docker container. It means that the machine used for launching should have docker installed. Then run the following commands:
```
docker-compose up -d
```
### .env file 
It should be filled according to this example:
```
SECRET_KEY=<Django secret key>
DB_ENGINE=django.db.backends.postgresql
DB_NAME=<name of db>
POSTGRES_USER=<username of db user>
POSTGRES_PASSWORD=<password of db user>
DB_HOST=db
DB_PORT=5432
```
### Migrations, static files and database fixtures
In order to make application up and running correctly, it is needed to perform django commands inside running container. 
Execute following commands:
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
```
### Load test database(not necessary)
To load test data into database you can run the following command:
```
docker-compose exec web python manage.py download_db
```
### API documentation
Full documentation for each API endpoint is available at:
```
http://localhost/redoc/
```
