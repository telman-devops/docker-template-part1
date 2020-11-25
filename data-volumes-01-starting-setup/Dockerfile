FROM node:14

WORKDIR /app

ADD package.json ./

RUN npm install

ADD . ./

ARG DEFAULT_PORT=80

ENV PORT $DEFAULT_PORT

EXPOSE $PORT

#VOLUME ["/app/node_modules"]


CMD ["npm", "start"]
