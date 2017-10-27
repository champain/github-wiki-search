FROM node:alpine as builder

ADD . /app

WORKDIR /app

RUN apk update
RUN apk upgrade
RUN apk add git

RUN yarn install
RUN ./node_modules/.bin/grunt vendor
RUN ./node_modules/.bin/grunt
RUN ./node_modules/.bin/grunt dist

FROM nginx:alpine

WORKDIR /usr/share/nginx/html/

COPY --from=builder /app/dist/ .
COPY nginx/default.conf /etc/nginx/conf.d/

CMD ["nginx", "-g", "daemon off;"]
