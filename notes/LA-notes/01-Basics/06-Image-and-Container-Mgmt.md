# Docker Image and Container Management

- We may be working around with many docker images and containers.
- Once the container has stopped then it will go to ***Exited*** status and those containers will remain as is.
- Also we'll be working with number of images and we might not need all of those.
- Depending on our need we can have them as is or else we need to remove those.
- To remove a container which is not running we need to use ***docker rm***

```
# docker rm <CONTAINER ID / NAME>
```

- To remove a docker image we need to use ***docker rmi***

```
# docker rmi <IMAGE-ID> / <REPOSITORY NAME with TAG>

Ex:

# docker rmi centos:centos6 (or)
# docker rmi 10611b26a8b9
```

- If we have containers running based on some images then we can't remove those. In case we want to remove then we will 2 choices
	- Stop the container if it is running and then remove it. Once the containers associated with that image were removed then we can remove the Images.

	```
	# docker ps -a | grep nginx:latest | awk '{print $1}' | xargs -r docker stop
	# docker ps -a | grep nginx:latest | awk '{print $1}' | xargs -r docker rm -v
	# docker images | grep 'nginx.*latest' | awk '{print $3}' | xargs -r docker rmi
	```

	- Else we can force the images to remove

	```
	docker images | grep 'nginx.*latest' | awk '{print $3}' | xargs -r docker rmi -f
	```
