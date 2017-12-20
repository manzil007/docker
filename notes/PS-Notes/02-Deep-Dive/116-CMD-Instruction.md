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
- 