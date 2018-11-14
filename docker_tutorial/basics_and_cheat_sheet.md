Source: [Docker official docs](https://docs.docker.com/get-started/#docker-concepts)

## Containerization
- The use of Linux containers to deploy applications is called containerization. Containers are not new, but their use for easily deploying applications is.
- Containerization is increasingly popular because containers are:
  - Flexible, Lightweight, Interchangeable, Portable, Scalable, Stackable
  - With Docker, _scaling_ your application is a matter of spinning up new executables, not running heavy VMs. 
- __Images and containers__: Container is launched by running an image. An image is an executable package that includes everything needed to run an application-- the code, a runtime, libraries, environment variables, and configuration files. A container is a runtime instance of an image--what the image becomes in memory when executed (that is, an image with state, or a user process).
- __Containers and VMs__: A container runs natively on Linux and shares the kernel of the host machine with other containers. It runs a discrete process, taking no more memory than any other executable, making it lightweight. By contrast, a virtual machine (VM) runs a full-blown “guest” operating system with virtual access to host resources through a hypervisor. In general, VMs provide an environment with more resources than most applications need.
- Containers make CI/ CD seamless. For example: 
  - applications have no system dependencies
  - updates can be pushed to any part of a distributed application
  - resource density can be optimized

## Cheat sheet

```console
## List Docker CLI commands
docker
docker container --help

## Display Docker version and info
docker --version
docker version
docker info

## Execute Docker image
docker run hello-world

## List Docker images
docker image ls

## List Docker containers (running, all, all in quiet mode)
docker container ls
docker container ls --all
docker container ls -aq
```
