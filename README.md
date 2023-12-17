# Dockerizing a Node.js Application

This repository contains a simple Dockerfile to containerize a Node.js application.

## Dockerfile Instructions

```dockerfile
FROM node:alpine

COPY . /app # copy current dir to /app in container file system, . can be some particular folder

WORKDIR /app

CMD node app.js # run command node app.js from workdir
```

To build the Docker image, use the following command:

```bash
docker build -t image_name .
```

If building on macOS with Apple Silicon CPU, use the following command instead:

```bash
docker build -t image_name --platform linux/amd64 .
```
(-t is tag, if want to push on docker hub, use username/image_name)

To create a repository on Docker Hub, use a name corresponding to the desired package:

- [Docker Hub](https://hub.docker.com/)
Create repo name as name of package you want, so same as image name is good

To push the Docker image to Docker Hub:

```bash
docker login -u username
# Enter your password when prompted

# If the image name is different from the repository name
docker tag image_name repo_name
docker image push repo_name

# If the image name is the same as the repository name
docker image push image_name
```

## Pull and Run from Docker Hub

To pull and run the Docker image from Docker Hub:

```bash
docker pull image_name
docker run image_name
```

Or directly:

```bash
docker run image_name
```
For a hands-on experience and testing, you can use [Docker Play Lab](https://labs.play-with-docker.com/).
