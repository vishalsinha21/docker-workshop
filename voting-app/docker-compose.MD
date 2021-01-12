## Voting app

[Official voting app repo](https://github.com/dockersamples/example-voting-app)

##### Setup voting app using docker imperative commands
- Build voting app with tag voting-app
- Build result app with tag result-app
- Build worker app with tag worker-app
- Run redis using image `redis:alpine` and name `redis`
- Run postgres using image `postgres:9.4` and name `db`. Also, supply environment variables POSTGRES_USER: "postgres" and POSTGRES_PASSWORD: "postgres"
- Run voting-app and expose it's port 80, link to databases as needed
- Run worker-app, link to databases as needed
- Run result-app and expose it's port 80, link to databases as needed

<details><summary>show</summary>
<p>

```bash
docker build ./vote -t voting-app
docker build ./result -t result-app
docker build ./worker -t worker-app

docker run -d --name=redis redis:alpine
docker run -d --name=db -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres postgres:9.4
docker run -d --link redis:redis -p 5000:80 voting-app:1.0
docker run -d --link redis:redis --link db:db worker-app
docker run -d --link db:db -p 5001:80 result-app

Voting app: http://localhost:5000/
Result app: http://localhost:5001/
```

</p>
</details>


##### Setup voting app using docker compose

<details><summary>show</summary>
<p>

```bash
Create a file docker-compose.yml with below configuration
version: "3"
services:
  vote:
    image: voting-app
    ports:
      - "5000:80"
  redis:
    image: redis:alpine
  worker:
    image: worker-app
  db:
    image: postgres:9.4
    environment:
      POSTGRES_USER: "postgres"
      POSTGRES_PASSWORD: "postgres"
  result:
    image: result-app
    ports:
      - "5001:80"

Execute
docker-compose up
or
docker-compose -f <docker-compose-config-filename> up
```

</p>
</details>


##### Here are some scenario based question. You don't have to implement now, but you should be aware of how these can be implemented. So imagine that you have a java application that needs Postgres database. 

How would you run the application with postgres running in container

<details><summary>show</summary>
<p>

```bash
Run postgres in a container, and expose it's port so java applciation can connect to it
```

</p>
</details>


How would you run both the application and postgres running in different container

<details><summary>show</summary>
<p>

```bash
Run postgres in a container
Run application in a container, and link them using --link. Application should use host as the service name of postgres.

or 
Use docker compose to run both the containers so they are linked. Application should still use host as the service name of postgres.
```

</p>
</details>