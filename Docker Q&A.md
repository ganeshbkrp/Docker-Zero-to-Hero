WHat is Docker?
Docker is a containerization technology which helps in containerizing your application. So your application can have all the components that are needed to run an application viz Base image, system dependencies, runtime libraries in one place. 

What is the difference between a Docker Container and VM?
Docker container is a lightweight standalone package of software which has code, libraries, runtime and system dependencies. Whereas a Virtual Machine has it's own OS CPU and Memory.Unlike containers Vms don't have a shared resources like CPU, memory etc. 
VMs are more secure than containers and there is complete isolation between two VMs.

What is Docker lifecycle?
Docker lifecycle is the journey from writing a dockerfile with the help of developers to building a docker image and creating a docker container from the Docker Image to containerize the application is called a docker lifecycle.

What is a Docker file?
Docker file is a set instructions given to the docker engine to build a Docker image with all the prerequisites, dependencies, instructions and requirements.

What is the difference between Docker ADD and Docker Copy?
Difference between Docker ADD and Docker Copy:- The Docker ADD command is used to transfer/move content from URLs onto the container while Docker Copy is used to copy the files from host machine onto the container.

What is the difference between Entrypoint and CMD?
Difference between Entrypoint and CMD is that they are both instructions which are defined in a docker file. CMD can be overridden by passing different parameters at runtime but entrypoint cannot be overridden so if you pass any variables in entrypoint while wriitng the docker file they do get executed irrespective of what is specified at runtime.

What are networking Types in Docker and what is the difference between them?
1. Bridge Networking - this is default networking used in Docker. Docker 0 is the default bride that connects the containers with each other and the underlying host.
2. Host Networking - Here the containers share the same networking stack as that of the underlying host and is least secure. Anyone who has access to the host will have access to the containers as well.
3. Overlay networking - This allows the containers to connect with other containers present on different hosts. Effectively containers present on different hosts are connected to a single network.
4. mavlan Netwokring - This allows the container to appear as a physical host rather than as a container on the network.

What is the default networking used in Docker? 
Default networking used in Docker is Bridge Networking.

How to isolate networking between containers? 
By using custom bridge networking we can isolate networking between two containers .

What is a multistage build in Docker?
Multistage build in Docker is a concept where we split the build process of the docker image into multiple parts with the primary objective of reducing the size of the Docker image. 
Most commonly we see two stages in the docker file wherein the second stage of the build process uses the artifacts of the first stage using an alias to contionue the build process. This also helps in building lightweight containers.

What is a Distroless Image?
Distroless Images in Docker are lightweight images which contain the bare minimum requuirements like system dependencies, runtime dependencies and application. They do not contain other packages, libraries and shell that are generally present in a Linux Distro.

What are the realtime issues faced while using Docker?
Realtime issues with docker that I faced were that Docker has a single point of failure where if the docjker Daemon fails or crashes all our contianers become unresponsive and we loose connection so it is a huge disadvantage for us in that sense. 
The host on whcih containers are running can sometimes run out of space/CPU/memory which can result in performance issues or crashes.
Docker daemon also runs via root user and incase the root user credentials gets compromised then it becomes a big security threat.

Podman and Buildah are two tools which have overcome the challenges docker gave by not having a single point of failure.


What steps would you take to secure your containers?
Steps taken to secure your containers:-

1. Use Distroless images as much as possible.
2. Use docker networking properly and use custom bridges wherever needed to isoalte infra at different levels.
3. Use utilities like Sync to scan your container images.

What are the components of Docker?

Docker has service/process called Docekrd or Dockerm Daemon which is the heart of the docker process. Docker client interacts with Docker daemon via the CLI and builds the docker imaghe from the dockerfile using the docker build instruction.
From the docker image a container can be built using the docker run command. We can connect to our cloud respository called dockerhub where we can store our docker images using docker push or docker pull command.
