FROM node:8.12.0-alpine

COPY . /application/
WORKDIR /application
RUN npm install
CMD node /application/src/server.js
