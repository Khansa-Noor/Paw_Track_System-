# Paw_Track_System-

A team of Web developers, working on a Pet Adoption and Fostering System, named as Paw_Track

# Group Memebers

1. Urba Naseem - Group Leader
2. Shiza Shahid - Collaborator #01
3. Syeda Ayesha Fatima - Collaborator #02
4. Fasiha Tariq - Collaborator #03
5. Khansa Noor - Collaborator #04

# Deliverable - 1

1. Created a basic home.html file
2. pushed on Git
3. Cloned by contributors
4. Contributors changes pushed to their respective branches
5. All the commits were merged into the main branch by the leader

# Deliverable - 2 (Building and Running Docker Images)

1. Create a Docker file
2. Build the docker image
   command : docker build --tag devops .
3. Run the docker image
   command : docker run -d -p 8080:80 devops:latest

# Deliverable - 3 (Added Backend Module and Created Docker-comper file)

1. Created Docker file for the Backend module
2. Created docker-compose.yml
3. Application is run through the Docker compose

# Activity 2

Making changes in the README.md file to test the jenkins software

# Change 2

Again just making minor change in the README file to generate build 2 in jenkins

# Deliverable 4 - Automating CI/CD Pipeline

## 1. Description of CI/CD Pipeline

This project uses a fully automated CI/CD pipeline implemented via **GitHub Actions**.

- **Trigger:** The pipeline triggers automatically upon a push to the `main` branch or when a Pull Request is merged.
- **Build & Test:** It checks out the code, builds a Docker image, and runs a simple container test to ensure the application starts correctly.
- **Push:** It authenticates with Docker Hub and pushes the latest image.
- **Deploy:** It connects to an AWS EC2 instance via SSH, pulls the newly built image, and restarts the application container.

## 2. Instructions to Run and Deploy the App

### Prerequisites

You need Docker installed on your local machine.

### Local Run

1. Build the Docker image:
   `docker build -t my-app .`
2. Run the container:
   `docker run -d -p 80:80 my-app`

### Automated Deployment

To deploy the application automatically via GitHub Actions, configure the following Secrets in your GitHub repository settings (`Settings > Secrets and variables > Actions`):

- `DOCKERHUB_USERNAME`: Your Docker Hub username.
- `DOCKERHUB_TOKEN`: Your Docker Hub access token.
- `EC2_HOST`: Your AWS EC2 instance public IP.
- `EC2_USER`: The SSH user (e.g., `ubuntu`).
- `EC2_SSH_KEY`: The private key (.pem content) to access the EC2 instance.

## 3. Changelog

### [v1.0.0] - 2026-11-04

- **Added:** GitHub Actions CI/CD workflow (`.github/workflows/ci-cd.yml`).
- **Added:** Automated deployment to AWS EC2 via SSH.
- **Added:** Automated build and push to Docker Hub.
- **Updated:** README.md with complete pipeline description, deployment instructions, and changelog.
