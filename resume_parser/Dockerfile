FROM python:3

ENV PYTHONUNBUFFERED 1

# set work directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
COPY requirements.txt /usr/src/app
RUN pip install -r /usr/src/app/requirements.txt
COPY . /usr/src/app
RUN python /usr/src/app/pre_requisites.py
RUN python /usr/src/app/manage.py flush --no-input
RUN python /usr/src/app/manage.py migrate
RUN python /usr/src/app/manage.py collectstatic --no-input