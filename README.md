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

# Deliverable - 2 (Building and Running  Docker Images)
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

Paw Track System uses GitHub Actions to automate the Continuous Integration and Continuous Deployment (CI/CD) process.

The workflow is defined in:

`.github/workflows/ci-cd.yml`

The pipeline automates Docker image building, container testing, and publishing images to Docker Hub.

### Pipeline Triggers

The workflow supports the following events:

1. **Push:** Automatically triggers when code is pushed to the main branch.
2. **Pull Request:** Runs when a pull request is opened, updated, or reopened against the main branch.
3. **Merged Pull Request:** Merging a pull request into main triggers the push event.
4. **Manual Execution:** Supports manually running the workflow through GitHub Actions.

### Pipeline Stages

1. **Checkout:** Retrieves the latest source code from GitHub.
2. **Build:** Builds separate Docker images for the frontend and backend.
3. **Test:** Starts both containers and checks whether the frontend and backend respond successfully.
4. **Docker Hub Login:** Authenticates using GitHub repository secrets.
5. **Push:** Publishes both Docker images to Docker Hub.

### Docker Hub Repositories

- Frontend: `fasiha21/pawtrack-frontend`
- Backend: `fasiha21/pawtrack-backend`

Images are published with two tags:

- `version4`
- GitHub commit SHA

### Security

Docker Hub credentials are stored securely in GitHub Actions repository secrets:

- `DOCKERHUB_USERNAME`
- `DOCKERHUB_TOKEN`

Credentials are not hardcoded into the workflow file.

## 2. Instructions to Run and Deploy the Application

### Prerequisites

- Git
- Docker Desktop
- Docker Compose
- GitHub account
- Docker Hub account

### A. Run Locally Using Docker Compose

Clone the repository:

```bash
git clone https://github.com/Fasiha-Tariq/Paw_Track_System-.git
```

Navigate to the project directory:

```bash
cd Paw_Track_System-
```

Build and start the application:

```bash
docker compose up --build -d
```

Check running containers:

```bash
docker ps
```

Open the application:

- Frontend: http://localhost
- Backend: http://localhost:8080/index.js

Stop the application:

```bash
docker compose down
```

### B. Pull Docker Images from Docker Hub

Pull the frontend image:

```bash
docker pull fasiha21/pawtrack-frontend:version4

```

Pull the backend image:

```bash
docker pull fasiha21/pawtrack-backend:version4
```

Verify downloaded images:

```bash
docker images
```

### C. Automated Deployment to Docker Hub

Whenever code is pushed to the main branch:

1. GitHub Actions automatically starts the CI/CD workflow.
2. Docker images are built.
3. Both containers are tested.
4. GitHub Actions authenticates with Docker Hub.
5. Updated frontend and backend images are pushed to Docker Hub.

The latest images are then available in the respective Docker Hub repositories.

---

## 3. Changelog

- Created GitHub Actions CI/CD workflow.
- Added multiple workflow trigger events.
- Automated frontend Docker image building.
- Automated backend Docker image building.
- Added frontend container testing.
- Added backend container testing.
- Integrated Docker Hub authentication using GitHub Secrets.
- Automated pushing of Docker images to Docker Hub.
- Added `version4` and Git commit SHA image tags.
- Updated project documentation with CI/CD instructions.
