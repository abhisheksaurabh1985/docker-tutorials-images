# docker-tutorials-images

# Docker image for Deep Learning and Computer vision
The docker image for deep learning and computer vision in this repository is built on top of the image maintained by [waleedka](https://github.com/waleedka).

## Steps to build this Docker image
1. Create a directory `container_name`: `mkdir container_name`
2. Copy this Dockerfile into that directory:`cp Dockerfile container_name/.`
3. Move to that directory:`cd container_name`
4. To build the docker file (might have to run with sudo):`sudo docker build -t container_name .`
After the successful build of the image, you will get the following output.
```bash
Successfully built a8571a7ef3f5 # a8571a7ef3f5 is the Image ID.
Successfully tagged deep_learning_opencv:latest # Note the tag 'latest'
```
5. Run `docker ps -a` to see if you have two containers: _container_name_ of about 4GB and _ubuntu_ image of about 114 MB.
