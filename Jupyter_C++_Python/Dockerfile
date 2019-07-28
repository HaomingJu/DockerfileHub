FROM jupyter/base-notebook

MAINTAINER juhaoming@126.com

USER root

RUN ["/bin/bash", "-c", "conda create -n cling  && conda init bash"]

COPY ./activate.sh /root/activate.sh

RUN chmod 777 /root/activate.sh && /root/activate.sh

EXPOSE 10000


# [Reference]
# https://github.com/QuantStack/xeus-cling
# https://hub.docker.com/r/jupyter/base-notebook
