-> Virtual servers came into being becasue the existing Physical servers were not utilized to the fullest.
-> Containers came into effect becasue the VMs were not utilized to the fullest. 

VMs have strong logical separation from each other. In containers that is not present. 
So as a result , there is overlapping of resources and containers also consume better compute resources than VMs.


->WHen we use docker as the containerization platform. We first write a docker file which is then converted to an image which is then executed to build a container.
All the above things can be done in a docker engine by running specific commands?

Docker build command is used to build images from docker files and docker run is used to build docker container from docker image.

The logical separation between two containers is the few files. The rest of the stuff i.e system dependencies the image should get it from the Kernel like CPU/RAM & Filesystem, Network resources etc.

Podman is a competeitor for Docker which also supports containerization.
Docker daemon is the heart of the containers. If Docker daemon goes down, all your docker containers will also go down.
Registry is a place where you save the docker images and share it with anyone in the world.

if you want to practise Docker on your Laptop/Dsktop you can use Docker Desktop
docker daemon runs using root user.

A good Devops Engineer should have knowledge of how coding works, how a particular application works. Understanding the worflow is important.

What is entry point and CMD in Docker?

Entrypoint will have non overrideable values.
CMD will have parameters which can be overridden or editable.

Distroless image is a very minimal image.
Biggest advantage of distroless images is security.
scratch is the minimalistic distroless image for Python.
multistage docker builds reduces the size fo the image drastically.


Bind Mounts binds a specific directory on the container with another directory on the host machine.
Volumes are a logical separation created on the host machine which can be attached/detached fromma container. 
It is created using the docker cli.
Volumes can be created on a host,ec2 machine, s3 and other external sources as well. 
It gives you the advantage of high availability.

There are two commands in docker volumes:

docker -v <__________>
docker --mount 

Both the commands are used for the same purpose but the docker --mount command is more verbose and has can be configured/customised according to your requirement.
Always go for Bind Volumes over Bind mounts as it has more advantages comparatively.


networking allows containers to communicate with each other and the host system as well.
Using container networking you can either isolate two containers or make them communicate with each other.

When a container is created a virtual eth networking is also created called as docker 0 which is  a bridged networking. This is responsible for communication.

There two types of Networking:
1. Bridge Networking
2. Host Networking
3. Overlay Networking


Docker compose:-

It is used to manage multi container application.

docker-compose up - to start the multi application containers
docker-compose down - to remove all the containers that are stopped.

If you’re on Windows or Mac and want to use Docker, Docker Desktop is usually the way to go.

On Linux servers, direct installation of Docker Engine is preferred for performance and resource efficiency.

Docker is the core technology (engine + CLI), while Docker Desktop is a packaged, graphical, and development-focused tool that wraps Docker (and more) for ease of use—especially on desktop platforms that don’t natively support Linux containers.

If you want to use docker compose, swarm you need to install additional packages which come inbuilt with docker desktop. unlike simple docker engine installation. 

You need a docker composed YAML file for using docker compose. When we have multi tiered application architecture it is easy to containerise using a docker compose than normal docker. 

docker compose is used when you have to do local development.
CICD
Testing(QE)

We cannot compare Kubernetes with Docker compose.
Kubernetes equivalent is docker swarm in docker ecosystem. 


Docker init:

Docker init is a cmd utility tool which scans your project directory and sets up the necessar docker related files making the process of application containerisation much faster.

Docker init generates the below files automatically.
1. Dockerfile
2. docker-compose.yml
3. .dockerignore

docker init does not build or run the application.
It speeds up the containerisation work flow. Sometimes the generated dockerfile may need external fine-tuning. 

You need docker desktop to use docker init. 


In one way docker compose is the AI version which generates you code when you enter a prompt. 

It is also the automated version where you enter the details when prompted and it gives you the necessary files. 

11/10/25

--> Docker Desktop/docker is inherently a Linux based container technology and for us to install Docker on a Windows desktop, we need to either enable/install WSL2 or Hyper-V(Virtualization). 
--> When it comes to Windows server we do not need any WSL2 or HyperV enabled/installed because docker engine supports Windows containers. Incase we wan to run Linux Containers on Windows Server thenwe need to install/enable WS2 to run the containers.
--> 
