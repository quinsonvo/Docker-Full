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
![2. Build Docker Image](RESULT_IMAGE/Step2.Build_Docker_Image.png)
### 3. Create file docker-compose.yml
With content:
```
version: "3.7"

services:
  app:
    image: learning-docker/node:v1
    restart: unless-stopped
```

### 4. Run docker image
```
docker compose up

```
![4. Run Docker Image](RESULT_IMAGE/Step4.Run_Docker_Image.png)

### 5. Shutdown container
```
docker compose down
```

### 6. App map port
Update docker-compose.yml:
```
ports:
      - "3000:3000"
```
Note: Left port is port in root environtment, right port is port in container

### 7. Run docker again
```
docker compose up -d
```
![7. Run Docker Image Again](RESULT_IMAGE/Step6_7.Add_map_port_and_run_docker_again.png)
See result in localhost:3000
![7. Run Docker Image Again](RESULT_IMAGE/Step7.png)
### 8 
