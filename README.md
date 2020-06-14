Test project for the new WSL2/Docker setup. Potential starting point for full project.

# Production

* docker-compose -f docker-compose.prod.yml up -d --build
* docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput
* docker-compose -f docker-compose.prod.yml exec web python manage.py collectstatic --no-input --clear

# Dev

* docker-compose up -d --build

# Env

### .env.dev of the form of:
```
DEBUG=1
SECRET_KEY=change_me
DJANGO_ALLOWED_HOSTS=localhost 127.0.0.1 [::1]
SQL_ENGINE=django.db.backends.postgresql
SQL_DATABASE=hello_django_dev
SQL_USER=user
SQL_PASSWORD=pass
SQL_HOST=db
SQL_PORT=5432
DATABASE=postgres
```

### .env.prod of the form of:
```
DEBUG=0
SECRET_KEY=change_me
DJANGO_ALLOWED_HOSTS=localhost 127.0.0.1 [::1]
SQL_ENGINE=django.db.backends.postgresql
SQL_DATABASE=hello_django_prod
SQL_USER=user
SQL_PASSWORD=pass
SQL_HOST=db
SQL_PORT=5432
DATABASE=postgres
```

### .env.prod.d of the form of:
```
POSTGRES_USER=user
POSTGRES_PASSWORD=pass
POSTGRES_DB=hello_django_prod
```

# File Tree

```
├── app
│   ├── hello_django
│   ├── mediafiles
│   ├── upload
│   ├── db.sqlite3
│   ├── Dockerfile
│   ├── Dockerfile.prod
│   ├── entrypoint.prod.sh
│   ├── entrypoint.sh
│   ├── manage.py
│   └── requirements.txt
├── nginx
│   ├── Dockerfile
│   └── nginx.conf
├── .env.dev
├── .env.prod
├── .env.prod.db
├── .gitignore
├── docker-compose.prod.yml
├── docker-compose.yml
└── README.md
```
