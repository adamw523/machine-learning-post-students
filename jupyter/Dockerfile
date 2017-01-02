FROM jupyter/scipy-notebook

USER root

RUN apt-get update && apt-get install -y libxml2-dev libxslt1-dev libffi-dev libssl-dev

ADD requirements.txt /
RUN pip install -r /requirements.txt

RUN cd /root/ && wget https://github.com/Calysto/notebook-extensions/archive/master.zip
RUN cd /root/ && unzip master.zip
RUN cd /root/notebook-extensions-master && jupyter nbextension install calysto --system && jupyter nbextension enable calysto/spell-check/main
