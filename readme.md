**Contenerizing 3 tier application on docker using docker compose ** BRIEF ABOUT THIS PROJECT: This project involves deploying a 3-tier MERN (MongoDB, Express.js, React, Node.js) application using Docker and Docker Compose for seamless containerization and orchestration. The architecture consists of three main services: a MongoDB database as the data layer, an Express.js and Node.js backend for API handling, and a React frontend for the user interface. Docker Compose simplifies multi-container management by defining services in a docker-compose.yml file, ensuring easy deployment, scaling, and maintenance. This approach enhances application portability, isolates dependencies, and enables efficient deployment across different environments. 🚀

A simple MERN stack application

Create a network for the docker containers: docker network create demo

Build the client: cd mern/frontend docker build -t mern-frontend .

Run the client: docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend

Verify the client is running: Open your browser and type http://localhost:5173

Run the mongodb container: docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest

Build the server: cd mern/backend docker build -t mern-backend .

Run the server: docker run --name=backend --network=demo -d -p 5050:5050 mern-backend

Using Docker Compose: docker compose up -d