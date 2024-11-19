## Flask Web Application with Load Balancer
This repository contains two Dockerized applications:

Webserver: A simple Flask web application that reads and displays a message from a configuration file.
Loadbalancer: An HAProxy load balancer that distributes incoming traffic among multiple webserver instances.
The setup is managed using Docker Compose, which makes it easy to build, run, and scale the services.

## Applications Overview
1. Webserver
A Flask application that:
Reads a message from a config.txt file.
Displays the message on the homepage via a web browser.
Exposed on port 5000 inside the container.
2. Loadbalancer
An HAProxy instance that:
Balances incoming HTTP traffic across multiple webserver instances.
Uses a round-robin load balancing algorithm to ensure even traffic distribution.
Exposed on port 80 inside the container.

## Project Structure
```
├── docker-compose.yml       
├── webserver/                 
│   ├── Dockerfile          
│   ├── app.py                 
│   └── config.txt             
└── loadbalancer/              
    ├── Dockerfile             
    └── haproxy.cfg            
```
## Prerequisites
Ensure you have the following installed:

Docker and Docker Compose

## Setup and Running the Application
### Step 1: 
Clone the Repository
### Step 2: Build and Run the Services
Use `docker compose up` to build and start the services
This command will Build the Docker images for webserver and loadbalancer.
Start both services:
The Flask webserver listens internally on port 5000.
The HAProxy load balancer listens externally on port 80.
### Step 3: Access the Application
Open your web browser and navigate to http://localhost.
The load balancer will route requests to the available webserver instances, displaying the message from config.txt.

## Stopping the Application
To stop the running containers, use: `docker compose down`
This command stops and removes the containers but retains the built images.
