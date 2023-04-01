# Asynchronous Web Service

## Description

This is a web service that uses the [FastAPI](https://fastapi.tiangolo.com/) framework to provide a REST API for a simple asynchronous web service. Task queues are implemented using [Celery](https://docs.celeryproject.org/en/stable/) with focus on real-time processing. [Redis](https://redis.io/) is used as an in-memory data structure store and process status from the task queue. [RabbitMQ](https://www.rabbitmq.com/) is used as a message broker for the task queue between FastAPI and the worker (Celery). The service is deployed using [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/).

## Start

Run the following commands to start the app:

```bash
sudo docker-compose up -d --build
```

## Endpoints

    - POST http://localhost:8000/api/process
        - Send one or more images to be processed, and receive a task ID in response.
    - GET http://localhost:8000/api/process/{task_id}
        - Get the status of a task by its ID.
    - GET http://localhost:8000/api/results/{task_id}
        - Get the results of a task by its ID.
    - GET http://localhost
        - Frontend for the web service and displays the results of the task from the API.
    - GET http://localhost:15672
        - RabbitMQ management interface.
    - GET http://localhost:8080/docs
        - FastAPI documentation interface.
