#### Basic docker commands

show docker version
```bash
docker version
```

run nginx
```bash
docker run nginx
```

run nginx in detached mode
```bash
docker run -d nginx
```

show all running containers
```bash
docker ps
```

show all containers (running/stopped)
```bash
docker ps -a
```

stop container
```bash
docker stop <container id | container name>
```

remove container permanently
```bash
docker rm <container id | container name>
```

list all images on system, along with size
```bash
docker images
```

remove image (stop and delete all containers using this image before deleting image)
```bash
docker rmi <image name>
```

pull image
```bash
docker pull <image name>
```

just run ubuntu image and see what happens
```bash
docker run ubuntu
```

run ubuntu and print date
```bash
docker run ubuntu date
```

execute command on docker container
```bash
docker exec <container name> <command>
```

attach to container
```bash
docker attach <container id | container name>
```

open bash on running container
```bash
docker exec -it <container name> bash
```

inspect container (gets more details)
```bash
docker inspect <container name | container id>
```

check container logs
```bash
docker logs <container name | container id>
```

run docker container providing a name
```bash
docker run --name <name> <image name>
```

docker run, login to container and run bash (i for interactive, t for terminal)
```bash
docker run -it <image> bash
```

port mapping/binding
```bash
docker run -p <local port>:<container port> <image>
```

volume/folder mapping
```bash
docker run -v <local folder>:<container folder> <image>
```

run image providing env variable
```bash
docker run -e <variable name>=<variable value> <image>
```

show containers in isolation, no file sharing
```bash
docker run -it busybox
docker run -it busybox
different file system
```
