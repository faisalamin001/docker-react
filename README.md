# Docker React App

This is a Dockerized React application that uses Vite for development and Nginx for production. This README provides instructions to build and run the Docker container for both development and production environments.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine
- A Docker Hub account (for pushing the Docker image)

## Build the Docker Image

To build the Docker image for your React application, follow these steps:

1. **Clone the Repository**:

   ```sh
   git clone https://github.com/faisalamin001/docker-react.git
   cd docker-react
   ```

2. **Build the Docker Image**:

   ```sh
   docker build -t docker-react .
   ```

## Run the Docker Container

### Development

To run the Docker container in development mode, follow these steps:

1. **Run the Container**:

   ```sh
   docker run -d -p 5173:5173 --name docker-react-dev docker-react
   ```

2. **Access the Application**:

   Open your browser and navigate to [http://localhost:5173](http://localhost:5173).

### Production

To run the Docker container in production mode, follow these steps:

1. **Build the Production Image**:

   ```sh
   docker build -t docker-react-prod --target production .
   ```

2. **Run the Container**:

   ```sh
   docker run -d -p 80:80 --name docker-react-prod docker-react-prod
   ```

3. **Access the Application**:

   Open your browser and navigate to [http://localhost](http://localhost).

## Push to Docker Hub

To push your Docker image to Docker Hub, follow these steps:

1. **Tag the Image**:

   ```sh
   docker tag docker-react your-dockerhub-username/docker-react:latest
   ```

2. **Log In to Docker Hub**:

   ```sh
   docker login
   ```

3. **Push the Image**:

   ```sh
   docker push your-dockerhub-username/docker-react:latest
   ```
