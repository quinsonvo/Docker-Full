# FOR DEV
### 1. Create Dockerfile with the following content:
```
FROM node:22

WORKDIR /app

COPY . .

RUN npm install

CMD ["npm", "start"]
```

### 2. Build Docker Image
docker build -t <image_name>:<tag> .

```
docker build -t learning-docker/node:v1 .
```