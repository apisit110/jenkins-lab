# FROM node:21-alpine3.18 AS builder
# USER node
# RUN mkdir -p /home/node/app
# WORKDIR /home/node/app
# RUN npm i -g turbo
# COPY . .
# COPY package*.json .
# COPY src .


FROM node:21-alpine3.18 AS builder
RUN apk update
# RUN apk install -y python3 make g++
USER node
RUN mkdir -p /home/node/app
WORKDIR /home/node/app
COPY --chown=node:node package*.json .
COPY --chown=node:node tsconfig.json tsconfig.json
COPY ./src ./src
RUN npm install
RUN npm run build


FROM node:21-alpine3.18 AS runner
USER node
RUN mkdir -p /home/node/app
WORKDIR /home/node/app
COPY --from=installer /home/node/app/dist dist

CMD ["node", "dist/index.js"]