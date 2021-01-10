## Basic Commands

##### Check the version of docker server

<details><summary>show</summary>
<p>

```bash
docker version
```

</p>
</details>

##### Run a nginx container

<details><summary>show</summary>
<p>

```bash
docker run nginx
```

</p>
</details>

##### List running containers

<details><summary>show</summary>
<p>

```bash
docker ps
```

</p>
</details>

##### Stop nginx container

<details><summary>show</summary>
<p>

```bash
docker stop <nginx container name|id>
```

</p>
</details>

##### Run a nginx container in detached mode

<details><summary>show</summary>
<p>

```bash
docker run -d nginx
```

</p>
</details>

##### List all containers (running as well as stopped)

<details><summary>show</summary>
<p>

```bash
docker ps -a
```

</p>
</details>

##### Check all the images

<details><summary>show</summary>
<p>

```bash
docker images
```

</p>
</details>

##### Run a container using redis images in detached

<details><summary>show</summary>
<p>

```bash
docker run redis
```

</p>
</details>

##### Stop the redis container

<details><summary>show</summary>
<p>

```bash
docker stop <container name or conatiner id>
```

</p>
</details>

##### Stop the nginx container

<details><summary>show</summary>
<p>

```bash
docker stop <container name or conatiner id>
```

</p>
</details>

##### Delete all containers

<details><summary>show</summary>
<p>

```bash
docker rm <container name or conatiner id>
```

</p>
</details>

##### Delete the nginx image

<details><summary>show</summary>
<p>

```bash
docker rmi nginx
```

</p>
</details>

##### Pull image nginx:1.14-alpine

<details><summary>show</summary>
<p>

```bash
docker pull nginx:1.14-alpine
```

</p>
</details>

##### Run a nginx container and check its logs

<details><summary>show</summary>
<p>

```bash
docker run nginx
docker logs <container name or container id>
```

</p>
</details>

##### Inspect nginx container and find current status

<details><summary>show</summary>
<p>

```bash
docker inspect <container name or container id>
```

</p>
</details>

##### Stop all running containers

<details><summary>show</summary>
<p>

```bash
docker rm <container name or container id> <container name or container id> <container name or container id> ...
```

</p>
</details>

##### Run ubuntu image

<details><summary>show</summary>
<p>

```bash
docker run ubuntu
```

</p>
</details>

##### Check if ubuntu container is running

<details><summary>show</summary>
<p>

```bash
docker ps
```

</p>
</details>

##### Run ubuntu container and execute date command

<details><summary>show</summary>
<p>

```bash
docker run ubuntu date
```

</p>
</details>

##### Run nginx container and map its port 80 on host port 8080, and access it

<details><summary>show</summary>
<p>

```bash
docker run -p 8080:80 nginx
```

</p>
</details>

##### Run ubuntu container passing 2 environment variable VAR1=VAL1 and VAR2=VAL2, and print all environment variable. Command to print all environment variable is `env`

<details><summary>show</summary>
<p>

```bash
docker run -e VAR1=VAL1 -e VAR2=VAL2 ubuntu env
```

</p>
</details>

##### Run mysql container, and map host volume `/data/mysql` to container volume `/var/lib/mysql`

<details><summary>show</summary>
<p>

```bash
docker run -d -v /data/mysql:/var/lib/mysql mysql
```

</p>
</details>




