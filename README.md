# Django REST Framework

Django REST framework is a powerful and flexible toolkit for building Web APIs.

See http://www.django-rest-framework.org for more information.

# Datatables

The stated goal of DataTables is "To enhance the accessibility of data in HTML tables".

See https://datatables.net/ for more information.

## Software versions

- python: 3
- django: latest
- djangorestframework-datatables: latest
- django-bootstrap4: latest
- django-rest-swagger: latest
- django-filter: latest
- mysqlclient: latest

## Usage

It's necessary to provide a volume to persist application code in your host. If you want to create a django application, provide an environment variable called "project" to docker run command. Your application will be created automatically.

Be aware that you only have to put as command the part after python manage.py, since python manage.py is entered automatically.

#### Create Django application 

This will create an application called DJANGO_PROJECT_NAME and serve it in port 80

```bash
docker run -d --name="django" -p 80:80 -e project=DJANGO_PROJECT_NAME -v HOST_DIRECTORY_DJANGO_PROJECT:/app pblasquez/django-rest-datatables runserver 0.0.0.0:80
```

#### Serve Django application 

This will serve a django application in port 80

```bash
docker run -d --name="django" -p 80:80 -v HOST_DIRECTORY_DJANGO_PROJECT:/app pblasquez/django-rest-datatables runserver 0.0.0.0:80
```

#### Create migrations

`docker exec -it django makemigrations`

#### Apply migrations

`docker exec -it django migrate`

#### Collect static files

`docker exec -it django collectstatic`
