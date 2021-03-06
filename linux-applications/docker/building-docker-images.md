<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [About](#about)
- [Example](#example)
  - [Dockerfile](#dockerfile)
  - [Build](#build)
  - [Push an image to Docker Cloud (Docker Hub)](#push-an-image-to-docker-cloud-docker-hub)
  - [Garbage cleanup](#garbage-cleanup)
- [Links](#links)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# About

Infomrmation on building docker images

# Example

## Dockerfile

`vim Dockerfile`
```
# our base image
FROM python:3-onbuild

# specify the port number the container should expose
EXPOSE 5000

# run the application
CMD ["python", "./app.py"]
```

## Build

The docker build command is quite simple - it takes an optional tag name with -t and a location of the directory containing the Dockerfile. Tagging ahead of is a good idea in case you don't want to push the image right away.

```
cd <DOCKER_PROJECT_DIR>
docker build --no-cache=true -t mike/testimage .
```

Although, for clean builds/rebuilds, it may be best to not include cache
```
cd <DOCKER_PROJECT_DIR>
docker build -t mike/testimage .
```

## Push an image to Docker Cloud (Docker Hub)

Before beginning, check your images
```
docker images
```

Example
```
# login
docker login

# tag image (if you have not already)
docker tag my_image <username>/my_image

# push image
docker push <username>/my_image
```

## Garbage cleanup

It is probably a good idea to include garbage collection steps, especially if you have scripted this with a Makefile.

CLI
```
sudo docker rmi $(sudo docker images -f "dangling=true" -q)
```

Makefile
```
sudo docker rmi `sudo docker images -f "dangling=true" -q`
```

See: http://www.projectatomic.io/blog/2015/07/what-are-docker-none-none-images/

# Links

* https://prakhar.me/docker-curriculum/
* https://docs.docker.com/docker-cloud/builds/push-images/
