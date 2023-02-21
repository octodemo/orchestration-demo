FROM node:8.1.2-alpine
RUN apk add --no-cache make gcc g++ python
RUN rm -rf /usr/src/pixi/web/uploads
RUN mkdir -p /usr/src/pixi/web
WORKDIR /usr/src/pixi/web
COPY app/package.json /usr/src/pixi/web
COPY app/package-lock.json /usr/src/pixi/web

RUN npm install --save
RUN npm install --save express 

COPY . /usr/src/pixi/web
COPY app/uploads/ /usr/src/pixi/web/uploads/

RUN npm install --unsafe-perm -g nodemon@1.11.0

EXPOSE 8000
CMD ["nodemon", "/usr/src/pixi/web/server.js"]
