FROM python:3.11-alpine

WORKDIR /usr/src/app

# Variables de entorno de Python
ENV PYTHONWRITEBYTECODE 1
ENV PYTHONBUFFERED 1

RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

COPY . .
