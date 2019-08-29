# docker-react
Short tutorial to frontend (fe) - backend (be) application which runs in separated docker containers. The communication (ports) is defined in minimalistic **docker-compose.yml**. Backend is written in Node.js and frontend in React.

## Frontend
Create basic React app with `npx create-react-app`, then create the `Dockerfile`
### Dockerfile
```
FROM node:alpine

RUN mkdir -p /fe
WORKDIR /fe

COPY package.json /fe
COPY package-lock.json /fe

RUN  npm install --production --silent

COPY . /fe

CMD ["npm", "start"]

```
>`FROM node:alpine`        - [Alpine Linux](https://alpinelinux.org/) "ISO" with Node.js preinstalled. The image is downloaded from the [DockerHub](https://hub.docker.com/_/node)

>`WORKDIR`                 - equivalent to `cd`

>`CMD ["npm", "start"]`     - equivalent to `npm start`

## Backend
