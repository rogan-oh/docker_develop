# Dockerfile
FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install python3-venv vim -y
RUN /usr/bin/python3 -m venv dataops
RUN /bin/bash -c "source dataops/bin/activate"
RUN /dataops/bin/pip3 install django
RUN mkdir /dataops/wsgi
RUN /dataops/bin/django-admin startproject wsgi /dataops/wsgi/
RUN rm -rf /dataops/wsgi/wsgi/settings.py

COPY ./dataops/settings.py /dataops/wsgi/wsgi


EXPOSE 8000

WORKDIR /dataops/wsgi
CMD ["/dataops/bin/python3", "manage.py", "runserver", "0.0.0.0:8000"]
