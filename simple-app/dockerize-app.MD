## Dockerfile

##### Dockerize simple bash script

<details><summary>show</summary>
<p>

```bash
FROM ubuntu

COPY app.sh .

CMD bash app.sh
```

</p>
</details>


##### Build image using Dockerfile, tag it as `simple-app`

<details><summary>show</summary>
<p>

```bash
docker build . -t simple-app
```

</p>
</details>

##### Run container using the image you created in interactive mode

<details><summary>show</summary>
<p>

```bash
docker run -it simple-app
```

</p>
</details>


##### Push this image to your public repository on dockerhub (create account on dockerhub if you don't have already)

<details><summary>show</summary>
<p>

```bash
docker login
docker build . -t <your-user-name>/simple-app
docker push <your-user-name>/simple-app
```

</p>
</details>