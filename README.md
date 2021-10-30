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

- running container -> image (files are stored in stopped container)
- `docker ps -a` all container  
- `docker ps -l`  last container  
- topped container has the software installed in it
- docker commit -> container to new image
- Run bash image `docker run -ti ubuntu:latest bash`
- create and give images name
- Run processes in containers
![dc run](images/dc-run.png)
![images file exists ](images/2021-10-25-10-26-03.png)

**Running process in Docker**

- containers have a min proceed
- one main process that has name
- -d run detached container in the background
## 3. Under the hood

Registries in detail

- Kernel : controls and organizes storage, programs and so. allocate resources and so on 
- docker manges kernel 
- cgroup to group process together 
- namespaces
- copy on write 
- make scripting distribution easy
- can be client and server 
  
- docker control socket
```
docker run -ti --rm -v /var/run/docker.sock docker sh
```
Docker network 

- Ethernet : move frame on wire of wifi
- IP layer : move packets on local network
- routing : forwards packets between networks 
- ports: address particular program on a computer 
- bridges -> virtual network on computer 
- controls the ethenes layer 
- docker builds bridges to create virtual network 
- Routing -> moving packets
- create fireball rule moves between network 
```sh
docker run -ti --rm --net=host --privileged=true ubuntu bash

apt-get update 
apt-get install iptables 
```
Exposing port is essentially port forwarding 


**Process in Docker** 

- process init 1-> to many process 
- shell -> runs other process -> continuer vanishes 
Intro to orchestration
```sh 
-> docker run -ti --rm --name qasim ubuntu bash 
-> docker inspect --format '{{.State.Pid}}' qasim
 3134

-> docker run -ti --rm --privileged=true --pid=host ubuntu bash
root@e63d21be00c6:/# kill 3134

root@99fb3caf034e:/# exit?
```

**storage in docker**
- actual storage 
- forms in logical groups 
- filesystem : which file belongs where 
- COWS!!! -> copy on write 
- base image -> write stuff container sees it with changes no change to the image 
- like a file system layer on the image !!! COW COPY ON WRITE 
- managing cows 
  - layers -> splits them to gzip files and then puts them on container 
  - containers are indigent of storage engine 
  - some have limited layers 
- get the right mount order correct 
**save abd load docker images**
  
1. save imaged locally 
![docker save](gitDocs/docker-save.png)
2. remove images 
![remove images](gitDocs/remove%20images.png) 
3. load Images 
![load images](gitDocs/load%20images.png)

