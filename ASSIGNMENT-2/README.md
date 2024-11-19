# Flask Application with Load Balancer and Docker

This repository contains a simple Flask web application that reads a message from a `config.txt` file and displays it on the homepage. The application is containerized using Docker and deployed with a load balancer (HAProxy) to distribute incoming traffic to multiple webserver instances.

## Files
- `Dockerfile` (in `./webserver`): The Dockerfile used to build the Docker image for the Flask application.
- `app.py` (in `./webserver`): The Python file containing the Flask application logic.
- `config.txt` (in `./webserver`): A text file that contains the message to be displayed on the homepage.
- `Dockerfile` (in `./loadbalancer`): The Dockerfile for the HAProxy load balancer.
- `haproxy.cfg` (in `./loadbalancer`): The configuration file for HAProxy.
- `docker-compose.yml`: A Docker Compose configuration to define and run both services (webserver and loadbalancer).

## Flask Application (`app.py`)

The `app.py` file defines a basic Flask web application that reads the content of `config.txt` and displays it on the homepage.

`