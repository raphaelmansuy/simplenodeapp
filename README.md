# simplenodeapp

A Dockerfile sample to build a node.js image

```Dockerfile
FROM node:10-alpine
RUN mkdir -p /src/app
WORKDIR /src/app

COPY ./src/package.json /src/app/package.json

RUN npm install 

COPY ./src /src/app

EXPOSE 3000

CMD ["npm","start"]
```

Shell command to build the image:

```bash
docker build -t helloworld-app:v1 .
```

Shell command to start a container for this newly created image:

```bash
docker run -it -d -p 3000:3000 helloworld-app:v1
```

Shell command to test if the nodejs web site is working:

```bash
curl http://localhost:3000
```
