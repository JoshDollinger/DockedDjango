Test project for the new WSL2/Docker setup. Potential starting point for full project.

# Production

* docker-compose -f docker-compose.prod.yml up -d --build
* docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput
* docker-compose -f docker-compose.prod.yml exec web python manage.py collectstatic --no-input --clear

# Dev

* docker-compose up -d --build
