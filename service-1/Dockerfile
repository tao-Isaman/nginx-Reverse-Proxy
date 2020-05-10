FROM python:3.9.0a6-alpine3.11
RUN apk update \
  && apk add gcc libc-dev g++ \
  && apk add libffi-dev libxml2 libffi-dev \
  && apk add unixodbc-dev mariadb-dev python3-dev
RUN mkdir /code
COPY . /code
WORKDIR /code
ENV FLASK_APP service.py
ENV FLASK_RUN_HOST 0.0.0.0
RUN pip install -r requirements.txt
RUN export FLASK_APP=service.py 
CMD ["flask", "run",]