# Docker Compose

## What?
Docker compose is a tool for designing and running multi-container applications.

## Why?
Docker Compose is mostly used as a helper when you want to start multiple Docker containers and doesn't want to start each one separately using.

*For example, suppose you had an application which required NGNIX and MySQL, you could create one file which would start both the containers as a service without the need to start each one separately.*

## How to install?
Click to [download](https://www.docker.com/products/docker-desktop) Docker.

If you using windows and mac os then no need install docker compose spretally. *But for other operating system then install using PIP command (python)*

```
pip install -U docker-compose
```
## How to check is installed?
* ``` docker-compose version ```
* ``` docker-compose --version ```
* ``` docker-compose -v ```

## How to create docker compose file?
```
version: '3.3'

services:
  ui:
    image: nginx:alpine
    container_name: UI
    restart: always
    ports:
      - 5000:80
    volumes:
      - .:/usr/share/nginx/html

  db:
    container_name: MongoDB
    image: mongo:latest
    restart: always
    ports:
      - 27017:27017
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: root

  mongo-express:
    container_name: MongoDB-Express
    image: mongo-express:latest
    restart: always
    ports:
      - 8081:8081
    environment:
      ME_CONFIG_MONGODB_ADMINUSERNAME: root
      ME_CONFIG_MONGODB_ADMINPASSWORD: root

```
## Basic Commands
* ``` docker-compose up ```
* ``` docker-compose ps ```
* ``` docker-compose down ```
