FROM node:alpine

ADD . /app

WORKDIR /app

RUN apk update
RUN apk upgrade
RUN apk add git

RUN yarn install
RUN ./node_modules/.bin/grunt vendor
RUN ./node_modules/.bin/grunt
RUN ./node_modules/.bin/grunt dist

CMD ["/bin/sh"]

#CMD ["nginx", "-g", "daemon off;"]
