![Docker](/images/dockericon-large.png)


***Definition*** : Docker is an open source project to pack, ship and run any application as a lightweight container.

- Through the docker containers we can pack customized applications which provides consistent way of packaging any application and shipping in a consistent way.

- The packaged application along with OS can be stored as an Docker Image and based on an Image number of containers can be launched as of our choice.

- We can prefer Docker as the containers are lightweight as compared to any VMs as this acts like OS level virtualization and it is open source.

- Docker communicates with the Linux Kernel through the following modules

```
libcontainer
libvert
LXC(Linux Containers)
systemd-nspawn
```

- Docker distinguishes three important concepts: 
	- docker machines
	- docker images
	- docker containers
	
- Docker containers are executions of an specific runtime environment. For example, to simulate a machine with an specific database up. These runtime environments are called Docker images, which are the result of executing the set of commands that appear in an specific script-like file called Dockerfile. Therefore, Docker allow having multiple containers of an specific Docker image. These could be compared with the concepts of program and process. Indeed, containers like processes, can be created, stopped, died, or running.

- Docker machines are local (and virtual) machines or remote machines(e.g in a cloud such as Amazon AWS or DigitalOcean) with a docker running. Like physical machines, docker machines has an specific IP address. Each docker machine can manage multiple docker images and containers. From our own personal computer, the docker-machine command, allow us connecting to all our docker machines to manage their containers and images.
