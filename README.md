# All You Need to Know - Docker (1-40)

- Containers: They are sealed, self-contained units of software that have everything needed to run a service.
What you should know(Viewed)

## 1. Installing Docker

<https://docs.docker.com/get-docker/>

## 2. Using Docker

**The Docker flow: Images to containers**

- Image -> running container
- `docker run docker-name`
- `docker ps` -> get information on running container
- image is fixed and does not change

**The Docker flow: Containers to images**

- runnning continer -> image (files are stored in stopped containr)
- `docker ps -a` all container  
- `docker ps -l`  last container  
- topped contianer has the software installed in it
- docker commit -> container to new image
- Run bash image `docker run -ti ubuntu:latest bash`
- create and give images name
- Run processes in containers
![dc run](iamges/dc-run.png)
![iamges file exists ](images/2021-10-25-10-26-03.png)

**Running process in Docker**

- containers have a min procees
- one main process that has name
- -d run detached contianer in the background

-
Manage containers

Exposing ports

Container networking

Legacy linking

Images

Volumes

Docker registries

## 3. Building Docker Images

What are Dockerfiles?

Building Dockerfiles

Dockerfile syntax

Multi-project Docker files

Avoid golden images

## 4. Under the Hood

Docker the program

Networking and namespaces

Processes and cgroups

Storage

## 5. Orchestration: Building Systems with Docker

Registries in detail

Intro to orchestration

Kubernetes in AWS

Google Kubernetes Engine

Conclusion
