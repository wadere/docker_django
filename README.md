# docker_django  [![Build Status](https://travis-ci.org/zsolthajdu/algoretum_django.svg?branch=master)](https://travis-ci.org/zsolthajdu/docker_django)
Docker container build script to create a python3/django development image.

## Usage
* Django app directory has to be mapped to /usr/src/app as docker volume.
* Set SITE_DIR environment variable to the name of the directory that stores the wsgi.py script.
* Another container, that provides the database', has to be connected as a docker link.

Example run : docker run --name django -e SITE_DIR="MySite" --link mysql_dj:mysql -p 8765:80 -v /home/user/dev/djangoapp:/usr/src/app -w /usr/src/app -d algoretum/django:latest tail -f /dev/null

