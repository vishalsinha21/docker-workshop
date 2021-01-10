## Voting app

##### Setup voting app using docker imperative commands

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
version: "3"

services:
  vote:
    build: ./vote
    command: python app.py
    volumes:
     - ./vote:/app
    ports:
      - "5000:80"

  redis:
    image: redis:alpine
    ports: ["6379"]

  worker:
    build: ./worker

  db:
    image: postgres:9.4
    environment:
      POSTGRES_USER: "postgres"
      POSTGRES_PASSWORD: "postgres"

  result:
    build: ./result
    command: nodemon server.js
    volumes:
      - ./result:/app
    ports:
      - "5001:80"
      - "5858:5858"

Execute
docker-compose up
```

</p>
</details>
