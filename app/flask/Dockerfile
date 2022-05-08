
FROM python:3.8-alpine

WORKDIR /app

ENV VIRTUAL_ENV=/opt/venv

RUN python3 -m venv $VIRTUAL_ENV

# RUN apt-get update && apt-get -y install gcc
# RUN apt-get update && apt-get install -y build-essential
# RUN apk add --no-cache gcc python3-dev
RUN apk add --no-cache gcc libc-dev linux-headers

COPY requirements.txt ./requirements.txt

RUN pip install -r requirements.txt

COPY . .

CMD [ "uwsgi", "--ini", "uwsgi.ini"]