FROM python:3-alpine

WORKDIR /opt
ADD ./code.tgz .
WORKDIR /opt/

RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev libffi-dev && \
    pip install -r requirements.txt

CMD uwsgi --http "0.0.0.0:8000" --module banana.wsgi --master --processes 4 --threads 2