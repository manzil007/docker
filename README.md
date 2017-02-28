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

# Docker engine dependencies from the Linux kernel

- The dependencies on the Linux kernel can be broadly categorized into 4 classes - resource constraining, security, networking, and storage.
	- Resource constraining features allow container creators to place restrictions on container environments like memory usage, cpu, etc.,.
	- Security features allow security policies to be applied on containers.
	- Networking features allow for the SDN networking features provided by Docker.
	- Storage features allow Docker to support volumes, and various storage backends.

![Kernel Dep1](/images/kernel-dep1.png) ![Kernel Dep2](/images/kernel-dep2.png)

# Resource Constraining Dependencies
- ***Control Groups (or) cgroups :***   
Control groups, or cgroups, is a kernel feature to constrain the resource usage of a process or a set of processes. This provides Docker with the following features:
	- Limit resources (CPI, memory, network, disk I/O, . . . ) to user-defined processes.
	- Prioritize resources to processes (a set of processes will get more resources than another set).
	- Measure resource usage for billing purposes.
	- Control a group of processes.

docker run command is used to manipulate resources allocated to a container. For instance, docker run --cpushares=<value> sets the cpu share allocated to a container (every container gets 1024 shares by default). docker run --cpuset-cpus=<value> sets the CPU core on which the container would be run.

Please refer to [Resource Management in Docker](https://goldmann.pl/blog/2014/09/11/resource-management-in-docker/) to know how to customize the resource utilization in Docker.

- ***Namespaces :***    
Namespaces is a kernel feature that provides lightweight process virtualization to containers. This helps Docker to isolate these resources for a container - process IDs, hostnames, user IDs, network access, IPC and filesystems. Docker combines namespaces and cgroups to isolate resources for containers and place resource usage constraints. These namespaces are used to isolate containers - Process ID (pid), Network (net), Mount (mnt), Hostname (uts), Shared Memory (ipc).
