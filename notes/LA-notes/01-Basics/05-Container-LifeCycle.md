# Docker Container LifeCycle

- Lifecycle of a docker container starts with ***docker run*** means from starting the container.

```
# docker run -d --name=MyWebTest1 nginx:latest
```

- Now we can see our running containers using the ***docker ps*** command. But we cannot get into that container as we didn't attached it to our terminal interactively.
- We can attach that running container to our terminal, even though we can't do anything on it as it has just the nginx process running on it but not the shell.
- In such case we can execute some additional commands on a running container like a bash shell. There after we can get into that container

```
# docker exec -it MyWebTest1 /bin/bash
# docker attach MyWebTest1
```

- In the above scenario we are running bash shell on the running container and then attaching it to our terminal.

