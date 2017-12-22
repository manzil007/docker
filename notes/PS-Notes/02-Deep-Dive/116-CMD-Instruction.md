# Instruction Set

- RUN
	- The commands passed through `RUN` will be executed at build time
	- After getting the base image we need to do some customizations like installing packages
	- Those executions can be added as `RUN` instructions
	- Every `RUN` instruction will add a new layer to the image
	- To avoid this we can join all the commands through `Logical AND`
- CMD
	- These are run time executions
	- The instructions which need to be executed at runtime of a container can be given as the CMD instructions
	- This is equilent to 
		- `docker run <args> <command>`
		- `docker run <args> /bin/bash`
	- Through out the Dockerfile only one CMD instruction is allowed
	- If we use more CMD instructions then the last one will be executed as everytime it gets overwritten
	- This is possible even if we give one CMD instruction in the Dockerfile and we give the commands at the run time through `docker run` command

| CMD | RUN |
|-----|-----|
| Run-Time | Build-Time |