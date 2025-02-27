# MERN Stack Application with Docker and AWS Deployment

This project is a full-stack MERN (MongoDB, Express.js, React, Node.js) application deployed using a CI/CD pipeline powered by GitHub Actions. The application is containerized using Docker and deployed to an AWS EC2 instance. The CI/CD pipeline automates the process of linting, testing, building, and deploying the application.

### Features

 Backend: Built with Node.js and Express.js, providing  APIs for the application.

 Frontend: Built with React, offering a dynamic and responsive user interface.

 Database: MongoDB for storing application data.

 Containerization: Docker is used to containerize both the frontend and backend services.

 CI/CD Pipeline: Automated using GitHub Actions for linting, testing, building Docker images, and deploying to AWS EC2.

### Prerequisites

Docker and Docker Compose installed.

AWS account with an EC2 instance.

Node.js and npm/yarn installed (for local development).


### Technologies Used

Frontend: React, Vite

Backend: Node.js, Express.js

Database: MongoDB

Containerization: Docker, Docker Compose

CI/CD: GitHub Actions

Cloud Deployment: AWS EC2

## CI CD pipeline

The GitHub Actions workflow consists of the following stages:

Linting and Testing:

2.Linting and testing the backend code using ESLint and Jest.

3.Build and Push Docker Images:

4.Building Docker images for the frontend and backend.

5.Pushing the images to Docker Hub.

6.Deploy to AWS EC2:

7.Pulling the latest Docker images on the EC2 instance.

8.Deploying the application using Docker Compose.

## Docker Compose

1.The docker-compose.yml file defines the services for the application:

2.Backend: Exposes port 5050 and connects to MongoDB.

3.Frontend: Exposes port 5173 and communicates with the backend API.

4.MongoDB: Persists data using a Docker volume.

## Environment Variables

1.The application uses environment variables for configuration stored in Github Secrets, such as:

2.MONGO_URI: Connection string for MongoDB.

3.DOCKER_HUB_USERNAME: Docker Hub username for pushing/pulling images.

4.EC2_PUBLIC_IP: Public IP of the EC2 instance for frontend API calls.


## How to Run the Project

1. Clone the repositary
git clone https://github.com/your-username/mern-app.git
cd mern-app

2. Set Up Environment Variables in your GithubSecrets:

DOCKER_HUB_USERNAME=your_docker_hub_username
MONGO_URI=your_mongo_uri
EC2_PUBLIC_IP=your_ec2_public_ip
etc

3. Run with Docker Compose:

docker-compose up -d

4.Access the Application:
Frontend: http://localhost:5173

Backend: http://localhost:5050

### GitHub Actions Workflow

The CI/CD pipeline is defined in .github/workflows/ci-cd.yml and includes:

Linting and testing the backend.

Building and pushing Docker images to Docker Hub.

Deploying the application to an AWS EC2 instance.






