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
Successfully tagged deep_learning_opencv:latest # Note the tag 'latest'. 'deep_learning_opencv' is the container name.
```
5. Run `docker ps -a` to see if you have two containers: __container\_name__ of about 4GB and __ubuntu__ image of about 114 MB.

## Run this docker image as a containers
__If you want to use OpenCV in your project as well, then use the run command as given in the section on *Display sharing from within the docker container*__.
```bash
docker run -it -p 8888:8888 -p 6006:6006 -v /sharedfolder:/root/sharedfolder container-name bash
```
Command parameters are explained below:
* -it: for creating a terminal to interact with the container_name
* -p 8888:8888 -p 6006:6006 : This exposes the ports inside the container so they can be accessed from the
                             host. The format is -p <host-port>:<container-port>. The default iPython Notebook
                             runs on port 8888 and Tensorboard on 6006
*  -v /sharedfolder:/root/sharedfolder: sharedfolder on host machine is shared with /root/sharedfolder in the container.
* container_name: Self-explanatory
* bash: Optional parameter. Even if this isn't provided, by default a bash session starts.

## Issues with running jupyter Notebook
This solution is taken from [this](https://stackoverflow.com/questions/38830610/access-jupyter-notebook-running-on-docker-container) on __stackoverflow__.
1. Inside the Container : `jupyter notebook --ip 0.0.0.0 --no-browser --allow-root`
2. On the host machine access this url : `localhost:8888/tree`

## Display sharing from within the docker container
This solution is taken from the instructions in  [this](https://github.com/oreillymedia/Learning-OpenCV-3_examples/blob/master/Dockerfile) opencv docker image.

1. Allow other processes to share the display. Run `xhost +` on your host machine.
2. Run the container:
```bash
sudo docker run -it -p 8888:8888 -p 6006:6006 \
	                  -e DISPLAY=$DISPLAY  -v /tmp/.X11-unix:/tmp/.X11-unix \
		                --device /dev/video0 \
	                  -v /shared/directory/on/host:/root/sharedfolder container-name bash
```      

‌​
