# emart-app
Containerized Microservices Project on AWS 🚀
Welcome to my Containerized Microservices Project! This repository showcases a robust ecommerce application built with Docker, orchestrated on an AWS t3.medium instance running Ubuntu 24.04 LTS. From development to deployment, this project highlights my journey in DevOps, cloud computing, and containerization. Let’s dive into the details! 🌟

🌟 Project Overview
This project containerizes a microservices-based ecommerce application, comprising:

NGINX: Acts as the API gateway and frontend, routing requests efficiently.
Angular Client: Delivers the user interface with a dynamic frontend.
NodeJS API: Manages backend data requests via a RESTful endpoint.
Java Books API: Handles book-related services, integrated with a MySQL database.
MongoDB: NoSQL database for the NodeJS API.
MySQL: Relational database for the Java API.

The source code is hosted in a monorepo structure, with each service defined in its own directory.

🎯 Key Achievements

AWS Deployment: Launched a t3.medium instance using the Ubuntu 24.04 LTS AMI via the AWS Management Console.
Containerization: Built custom Docker images for all microservices with tailored Dockerfiles.
Orchestration: Utilized Docker Compose to manage and run the multi-container setup.
Monitoring: Tracked real-time logs with AWS CLI and Git logs for seamless operation.
Publishing: Uploaded images to Docker Hub for reusability.
Cleanup: Terminated the AWS instance and pruned resources post-testing.

This project enhanced my skills in cloud infrastructure, container management, and DevOps practices.

📋 Getting Started
Prerequisites

AWS Account: For launching the t3.medium instance.
Docker: Installed on the instance (sudo apt install docker.io -y).
Git: For cloning the repository (sudo apt install git -y).
Docker Compose: Installed (sudo apt install docker-compose -y).
VS Code (optional): For code editing (code .).

Installation Steps

Launch AWS Instance:

In AWS Console, select "Launch Instance," choose Ubuntu 24.04 LTS AMI, set t3.medium, generate a key pair (e.g., mykey.pem), and configure security group (ports 80, 22).
SSH: ssh -i mykey.pem ubuntu@<AWS-IP>.


Clone Repository:

git clone <repo-ssh-url>
cd vprofile-project


Build Containers:

Edit Dockerfiles in client, javaAPI, nginx, nodeAPI.
Run docker build -t myapp:latest . in each directory.
Verify with docker images.


Orchestrate with Docker Compose:

Create/edit docker-compose.yml for NGINX, MongoDB, MySQL, and APIs.
Start: docker-compose up -d
Check: docker ps


Access Application:

Open http://<AWS-IP> in browser (port 80).
Monitor logs: docker logs <container-id> or aws logs get-log-events --log-group-name /aws/ec2/<instance-id>.


Publish to Docker Hub:

Log in: docker login
Tag: docker tag myapp:latest <your-account>/myapp:latest
Push: docker push <your-account>/myapp:latest


Cleanup:

Stop: docker-compose down
Prune: docker system prune -a
Terminate: AWS Console "Terminate" or aws ec2 terminate-instances --instance-ids <instance-id>




🛠️ Technologies Used

AWS: t3.medium, Security Groups.
Ubuntu: 24.04 LTS AMI.
Docker: For containerization.
Docker Compose: For orchestration.
Git: For version control.
VS Code: For development.


📊 Project Structure
vprofile-project/
├── client/          # Angular frontend
├── javaAPI/         # Java Books API
├── nginx/           # API gateway
├── nodeAPI/         # NodeJS API
├── docker-compose.yml


🤝 Contributions & Collaboration
This project is possible because of the community. You may:

Fork the repository: https://github.com/devopshydclub/emartapp.git
Submit pull requests with improvements.
Suggest enhancements in the Issues tab.


📜 License
MIT License - Free to use, modify, and distribute.

#DevOps #AWS #Docker #Microservices #Ubuntu24 #Containerization #TechJourney #CloudComputing #OpenSource