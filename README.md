# MERN Stack Application with Docker and AWS Deployment

This project is a MERN (MongoDB, Express.js, React, Node.js) stack application containerized using Docker and deployed on AWS EC2. 
It demonstrates best practices for containerization, environment variable management, and CI/CD integration using GitHub Actions and Jenkins.

### Features

Frontend: React app served on port 5173.

Backend: Node.js/Express app served on port 5050.

Database: MongoDB running in a Docker container.

Docker Compose: Simplifies local development and deployment.

AWS Deployment: Step-by-step guide to deploy the app on an EC2 instance.

CI/CD: Integration with GitHub Actions and Jenkins for automated testing and deployment.


### Prerequisites

Docker and Docker Compose installed.

AWS account with an EC2 instance.

Node.js and npm/yarn installed (for local development).


### Getting started

## Deployment on AWS EC2

1. Launch an EC2 Instance
Use an Ubuntu AMI.

Configure the security group to allow inbound traffic on ports:

22 (SSH)

5050 (Backend)

5173 (Frontend)

27017 (MongoDB)

2. SSH into the EC2 Instance

ssh -i your-key.pem ubuntu@ec2-public-ip

3. Install Docker and Docker Compose
sudo apt update
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

4. Clone the Repository

git clone https://github.com/your-username/your-repo.git
cd your-repo

5. Set Up Environment Variables
Create a .env file in the backend and frontend directories with the following variables:

# Backend .env
MONGO_URI=mongodb://mongodb:27017/mydatabase
PORT=5050

# Frontend .env
VITE_API_URL=http://backend-ip-address:5050

6. Start the Application
docker-compose up --build -d

7. Access the Application

Frontend: http://ec2-public-ip:5173

Backend: http://ec2-public-ip:5050


