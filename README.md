# Dockerized Flask and Nginx Web Application

## Overview
This project is a Dockerized web application using **Flask** as the backend and **Nginx** as a reverse proxy server. The application retrieves and displays key user information, including the IP address, MAC address, system username, and a timestamp, rendered on a simple HTML page. This project demonstrates the integration of Docker, Flask, and Nginx, showcasing the setup of a reverse proxy and a containerized application architecture.

## Features
- **Flask Web Application**: A basic Flask app to retrieve and display user details.
- **Nginx Reverse Proxy**: Nginx acts as a reverse proxy server for the Flask app, optimizing performance and providing additional security.
- **Docker Integration**: Both the application and Nginx server are containerized using Docker and Docker Compose, ensuring a consistent and portable environment.

## Getting Started

### Prerequisites
Make sure you have Docker and Docker Compose installed on your local machine:
- **Docker**: [Install Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Install Docker Compose](https://docs.docker.com/compose/install/)

### Clone the Repository
Clone this repository to your local device:
```bash
   git clone <repository-url>
   cd <repository-folder>
```

## Project Structure
- **/python**: Contains the Flask application with its Dockerfile.
- **/nginx**: Contains the Nginx configuration files and Dockerfile for the Nginx server.
- **/Screenshots**: Contains the screenshots of the application running on the web browser, and the logs history of nginx build after running ```docker-compose up --build```.
- **/Report on Issues Faced and Resolutions in Docker Application Deployment
Introduction**: Contains the brief report on the Assignment done.

## Running the Application Locally
To set up and run the application locally, follow these steps:
1. **Build the Docker Image from the docker file by using:
   ```bash
   cd nginx
   docker build -t local-nginx .
   ```
   ```bash
   cd python
   docker build -t local-python-app .
   ```

2. **Build the Docker Images**: Use Docker Compose to build and set up the containers:
   ```bash
   docker-compose up --build

This command builds both the Flask app and Nginx images and then starts the containers.

3. **Access the Application**: Once the containers are up and running, open a web browser and go to:
   ``` http://localhost```
   You should see the application's web page displaying IP address, MAC address, username, and timestamp information.

## Stopping the Application
To stop the containers, press Ctrl+C in the terminal where Docker Compose is running, or run:
   ```bash
   docker-compose down
```
## Technologies Used
1. Python (Flask)
2. Nginx
3. Docker and Docker Compose

## TroubleShooting
1. **Port 80 Already in Use:** If youu encounter an error that port 80 is already allocated, ensure no other service is using port 80 on your machine, or update the ```docker-compose.yaml``` file to epose to different port.
2. **Syntax or Connectivity Issues:** For syntax errors or connectivity issues, check the DockerFile and nging.conf files for any typos or misconfigurations.
3. **For Container Already in Use:** If an error shows stating that container is already in use, either kill that container first and the build the ```docker-compose.yaml``` or rename the container name  ```proxy_pass http://python-app-service:8000``` in the ```nginx.conf``` file.

## Author
Harsh Kumar

