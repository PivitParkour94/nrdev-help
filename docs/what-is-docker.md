[Docker](https://www.docker.com/) is a great tool for playing with lots of different operating systems and stacks without worrying about things getting permanently messed up on your computer.

## Docker Images
Images are created as essentially automatically provisioned computers (Linux/windows etc) which are built using a special script called a Dockerfile. They are made of layers and each layer is cached to speed up building of images. 

The benefit of Docker images is you never have an inconsistent state between your version of an image and someone else's. No more "it works on my machine 🤷‍♂️" situations!

Docker has a whole [list of community built and maintained Docker images](https://hub.docker.com/) for all sorts of tasks/purposes, from [MySQL](https://hub.docker.com/_/mysql) and [Apache servers](https://hub.docker.com/_/httpd) to [Minecraft servers](https://hub.docker.com/r/itzg/minecraft-server).

Once you understand what a Docker image is, you might want to ask "Ok, so if this magical pre provisioned computer exists, where do I access it?". That's where Docker containers come in. 

## Docker Containers
A Docker container is a running version of the docker image.

The most common usage for development is to run your Docker image directly on your computer, as a virtual machine. This can be accomplished by running the command `docker run hello-docker` where `hello-docker` is the image name (this is where you can start being creative and spin up other images)

One of the main benefits with using Docker is you can spin up containers willy nilly and they'll spin up perform their task then go away. While they're up you have a perfectly functioning playground to do whatever you'd like, and if you break something, no worries, just spin up a new version of the same image. That's the point.

So get out there and start spinning up containers for all of your different tasks, and later on I'll talk about ways to automate the deployment of multiple containers with different purposes using [Docker compose](https://docs.docker.com/compose/)

## Useful Commands
```
# build a Docker image called nates-dev
docker build -t nates-dev /home/nate/path/to/build/image -f /path/to/Dockerfile

# run nates-dev container
docker run -i nates-dev

# list running containers
docker ps

# open the container's shell interactively
docker exec -it <container_id> /bin/bash

# stop a running container
docker stop <container_id>
```
