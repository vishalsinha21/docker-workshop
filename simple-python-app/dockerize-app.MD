## Dockerfile

##### Dockerize simple bash script

<details><summary>show</summary>
<p>

```bash
# set base image (host OS)
FROM python:3.8

# set the working directory in the container
WORKDIR /code

# copy the dependencies file to the working directory
COPY requirements.txt .

# install dependencies
RUN pip install -r requirements.txt

# copy the content of the local src directory to the working directory
COPY src/ .

# command to run on container start
CMD [ "python", "./server.py" ]
```

</p>
</details>


##### Build image using Dockerfile

<details><summary>show</summary>
<p>

```bash
docker build . -t simple-python-app
```

</p>
</details>

##### Run container using the image you created

<details><summary>show</summary>
<p>

```bash
docker run -d -p 5000:5000 simple-python-app
```

</p>
</details>


##### Check output

<details><summary>show</summary>
<p>

```bash
curl localhost:5000
```

</p>
</details>