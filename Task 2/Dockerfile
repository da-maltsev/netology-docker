# base image
FROM python:3.8-slim

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# workdir
RUN mkdir /code
WORKDIR /code
COPY ./stocks_products /code

# install dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# migrate database
RUN python3 manage.py migrate

EXPOSE 8000

CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]