FROM node:10.16-alpine

RUN mkdir -p /srv/md5-file/md5-fe
WORKDIR /srv/md5-file/md5-fe

COPY package.json /srv/md5-file/md5-fe
COPY package-lock.json /srv/md5-file/md5-fe

RUN apk add --no-cache make gcc g++ python && \
  npm install --production --silent && \
  apk del make gcc g++ python

COPY . /srv/md5-file/md5-fe

CMD ["npm", "start"]

