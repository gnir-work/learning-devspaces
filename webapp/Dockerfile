FROM node:18

RUN mkdir -p /app/webap
WORKDIR /app/webapp

COPY ./package.json ./yarn.lock /app/webapp/
RUN yarn install
COPY ./index.html ./vite.config.js ./public /app/webapp/
COPY ./src ./public /app/webapp/src/

CMD ["yarn", "run", "dev"]