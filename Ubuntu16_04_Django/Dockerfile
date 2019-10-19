# Django + uwsgi + Nginx
#
# VERSION               0.0.1

FROM     ubuntu:16.04
MAINTAINER  Haoming.Ju "juhaoming@126.com"

RUN apt-get -y update

RUN apt-get install -y python2.7
RUN apt-get install -y python-pip
RUN python -m pip install "django<2"
RUN pip install uwsgi
RUN apt-get install -y nginx

RUN apt-get install git
RUN git config --global user.name "Docker.Ju"
RUN git config --global user.mail "Docker.Ju@Trunk.tech"


EXPOSE 8000
