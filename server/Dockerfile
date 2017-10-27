FROM python:2.7.14-alpine3.6

RUN apk update
RUN apk upgrade
RUN apk add --no-cache --virtual build-dependencies \
    gcc make g++ ca-certificates zlib-dev libffi-dev \
    libxml2 libxslt libxslt-dev libxml2-dev

ADD . /app

WORKDIR /app

RUN pip install -r requirements.txt

CMD ["python"]

# TODO figure out entrypoint
