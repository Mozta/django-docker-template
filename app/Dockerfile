FROM python:3.11-alpine

WORKDIR /usr/src/app

# Variables de entorno de Python
ENV PYTHONWRITEBYTECODE 1
ENV PYTHONBUFFERED 1

# install psycopg2 dependencies
RUN apk update \
    && apk add postgresql-dev gcc python3-dev musl-dev jpeg-dev zlib-dev pango openjpeg-dev g++ libffi-dev

RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

COPY ./entrypoint.sh .
RUN sed -i 's/\r$//g' /usr/src/app/entrypoint.sh
RUN chmod +x /usr/src/app/entrypoint.sh

COPY . .

ENTRYPOINT [ "/usr/src/app/entrypoint.sh" ]
