## Containerization
- __Source__: [Docker official docs](https://docs.docker.com/get-started/#docker-concepts)

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

## Understanding how the Docker Daemon and Docker CLI Work Together
- __Source__: [Nick Janetakis's blog](https://nickjanetakis.com/blog/understanding-how-the-docker-daemon-and-docker-cli-work-together)

__Key Points__
- It has a client-server architecture. 
- The __Docker daemon__ is a service that runs on your host operating system. It currently only runs on Linux because it depends on a number of Linux kernel features, but there are a few ways to run Docker on MacOS and Windows too.
- The Docker daemon itself exposes a __REST API__. From here, a number of different tools can talk to the daemon through this API.
- The most widespread tool is the __Docker CLI__. It is a command line tool that lets you talk to the Docker daemon. When you install Docker, you get both the Docker daemon and the Docker CLI tools together.

![alt text](https://nickjanetakis.com/assets/blog/docker-client-host-registry-fc0858b5191e042ce19437fd6b52ba214d1e429bf646374f633598ebaac1a4ab.jpg)

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
