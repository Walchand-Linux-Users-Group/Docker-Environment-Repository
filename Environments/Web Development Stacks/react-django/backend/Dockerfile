FROM python:3.12

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    libpq-dev

COPY requirements.txt /app/requirements.txt

RUN pip install --upgrade pip setuptools wheel
RUN pip install -r /app/requirements.txt

COPY . /app
EXPOSE 8000

#dev deploy
# CMD ["/bin/bash","-c","python manage.py migrate && python manage.py runserver"]

# production deploy
CMD ["/bin/bash","-c","python manage.py migrate && gunicorn backend.wsgi:application --bind 0.0.0.0:8000 --workers 3"]
