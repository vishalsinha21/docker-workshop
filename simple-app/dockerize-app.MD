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


##### Build image using Dockerfile

<details><summary>show</summary>
<p>

```bash
docker build . -t simple-app
```

</p>
</details>

##### Run container using the image you created

<details><summary>show</summary>
<p>

```bash
docker run -it simple-app
```

</p>
</details>
