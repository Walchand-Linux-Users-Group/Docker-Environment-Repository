
# Description

Dockerfiles for quick and easy containerised deployment of react and django-rest project with postgres database

## Getting Started

make sure you have docker installed in your system.

#### react
start coding your react app inside src  in frontend folder.

#### django
add your django code in backend folder.
make sure to setup database as postgres in django settings.py
``` 
DATABASES = {
    'default': {
        'ENGINE': django.db.backends.postgresql,
        'NAME': os.environ.get('POSTGRES_NAME'),
        'USER': os.environ.get('POSTGRES_USER'),
        'PASSWORD': os.environ.get('POSTGRES_PASSWORD'),
        'HOST': os.environ.get('POSTGRES_HOST'), 
        'PORT': os.environ.get('POSTGRES_PORT'), 
    }
}
```
Add these environment variables to configuration in settings.py
```
SECRET_KEY = os.getenv("DJANGO_SECRET_KEY")
ALLOWED_HOSTS = os.getenv("DJANGO_ALLOWED_HOSTS").split(",")
```
Add your details in .env file
```
DJANGO_SECRET_KEY=<secret key>
DJANGO_ALLOWED_HOSTS=localhost
POSTGRES_NAME=<database_name>
POSTGRES_USERNAME=<database_user>
POSTGRES_PASSWORD=<database_password>
```
### Running with docker compose
```
 docker compose up
```
or to run in detached mode
```
 docker compose up -d
```

## features
* support for both developement deploy and production ready deployment containers
* Standard port mapping for all services, configurable in docker-compose.yaml



