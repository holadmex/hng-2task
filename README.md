# Full-Stack FastAPI and React Template

Welcome to the Full-Stack FastAPI and React template repository. This repository serves as a demo application for interns, showcasing how to set up and run a full-stack application with a FastAPI backend and a ReactJS frontend using ChakraUI.

## Project Structure

The repository is organized into two main directories:

- **frontend**: Contains the ReactJS application.
- **backend**: Contains the FastAPI application and PostgreSQL database integration.

Each directory has its own README file with detailed instructions specific to that part of the application.

## Getting Started

To get started with this template, please follow the instructions in the respective directories:

- [Frontend README](./frontend/README.md)
- [Backend README](./backend/README.md)


## Local Development test for Full Stack Web Application.


clone the project repository on your local environment 

```sh
git clone https://github.com/holadmex/hng-2task.git

```

## Prerequisites installation in running your frontend

- Node.js (version > 14)

## Setup Instructions

1. **Navigate to the frontend directory**:
    ```sh
    cd frontend
    ```

2. **Install dependencies**:
    ```sh
    npm install
    ```

3. **Run the development server**:
    ```sh
    npm run dev
    ```


## Prerequisites installation in running your backend

- Python 3.8 or higher
- Poetry (for dependency management)
- PostgreSQL (ensure the database server is running)

### Installing Poetry

To install Poetry, follow these steps:

```sh
curl -sSL https://install.python-poetry.org | python3 -
```

Add Poetry to your PATH (if not automatically added):

## Setup Instructions

1. **Navigate to the backend directory**:
    ```sh
    cd backend
    ```

2. **Install dependencies using Poetry**:
    ```sh
    poetry install
    ```

3. **After your PostgreSQL installation**
   **Run the following commands**
   ```sh
   sudo -u postgres psql
   CREATE DATABASE app;
   CREATE USER app WITH ENCRYPTED PASSWORD 'changethis123';
   GRANT ALL PRIVILEGES ON DATABASE app TO app;
   psql -h localhost -U app -d app
   

4. **Set up the database with the necessary tables**:
    ```sh
    poetry run bash ./prestart.sh
    ```

5. **Run the backend server**:
    ```sh
    poetry run uvicorn app.main:app --reload
    ```

On implementing all of the above steps, you should have your frontend/backend-database application running locally.

## Now, we'll be moving to containerization of our local development locally

**Prerequisite Installation**

1. Docker Engine (Linux) Docker Desktop (Windows)
2. Docker Compose

#After installing Docker, add ubuntu user to docker group
```sh
sudo usermod -aG docker ubuntu
```

Each frontend/backend directory has its own **Dockerfile**

Also, have written a docker-compose.yaml file which will help in building the process to streamline build of docker images and also containerizing them just all at one stop shop. The docker-compose.yml is at the root of our project directory

The stipulated commands below helps to execute out docker compose function

```sh
docker-compose up -d --build
```
## Few things to take note of in the docker-compose.yaml file

Docker compose is going to **cd** into both my frontend/backend directory to build each **Dockerfile** therein, and also it will pull the following container images from **DockerHub** 

1. Nginx-proxy-manager (This is a user-friendly interface for managing Nginx proxy hosts.)
2. Postgres (This will make use of our backend/.env file configuration)
3. Adminer (This is a lightweight database management tool.)

**While our docker compose build has successfully finished running, browse the following web address on your web browser for local development test of your web application running locally.

```sh
localhost
localhost:8080
localhost:8000/api
localhost:8000/docs
localhost:8000/redoc
```
