# FROM python

# WORKDIR /usr/app/src

# COPY html /var/
# COPY Python/demo.py $WORKDIR

# # RUN apt-get update
# # RUN apt-get -y install nginx

# CMD ["python","./demo.py"]

# syntax=docker/dockerfile:1
FROM python:3.10-alpine
WORKDIR /code
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0
RUN apk add --no-cache gcc musl-dev linux-headers
COPY Python/requirements.txt requirements.txt
RUN pip install -r requirements.txt
EXPOSE 5000
COPY Python/app.py .
CMD ["flask", "run", "--debug"]