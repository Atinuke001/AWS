FROM python:3.5-alpine
ENV PYTHONUNBUFFERED 1
RUN set -e; \
        apk add --no-cache --virtual .build-deps \
                gcc \
                libc-dev \
                linux-headers \
                mariadb-dev \
                python3-dev \
                postgresql-dev \
        ;
RUN mkdir /djcode
WORKDIR /djcode
ENV REFRESHED_AT 2017-12-25
ADD requirements.txt /djcode/
RUN pip install --no-cache-dir -r /djcode/requirements.txt
RUN pip install uwsgi
ADD . /djcode/
EXPOSE 6001