# Dockerfile
FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install python3-venv -y
RUN /usr/bin/python3 -m venv dataops
RUN /bin/bash -c "source dataops/bin/activate"
RUN /dataops/bin/pip3 install django
RUN /dataops/bin/django-admin startproject wsgi /dataops/
