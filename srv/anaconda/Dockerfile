FROM continuumio/anaconda3

ADD ./srv/anaconda/conf/requirements.txt /

RUN apt-get -y install gcc && pip install --upgrade setuptools && pip install -r requirements.txt
RUN mkdir -p /root/.jupyter
COPY ./srv/anaconda/conf/jupyter_notebook_config.json /root/.jupyter/jupyter_notebook_config.json

EXPOSE 8888
