Title: Create any three-tier application using Docker.
---
## Three-tier application using Docker.

# Create any three-tier application using Docker.

## Prerequisites

Before you begin, ensure that you have the following installed:

- [Docker](https://www.docker.com/get-started)

## Project Structure

- **backend**: Node.js .
- **frontend**: Angular.
- **database**: SqLite.

## Dockerfile(Backend)

![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/docback.png)

## Dockerfile(Frontend)

![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/docfront.png)

## nginx.conf(Frontend)

![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/ngnix.png)

## Deployment Steps

0. **Backend Application:**

   - Navigate to the `backend` directory.
   - Build the backend Docker image:
     ```bash
     docker build -t 21bcp435d-backend .
     ```
     ![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/buildback.png)
   - Run the backend container:
     ```bash
     docker run -d -p 3000:3000 21bcp435d-backend 
     ```
     ![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/runback.png)

1. **Frontend Application:**

   - Navigate to the `frontend` directory.
   - Build the frontend Docker image:
     ```bash
     docker build -t 21bcp435d-frontend .
     ```
     ![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/buildfront.png)
   - Run the frontend container:
     ```bash
     docker run -d -p 80:80 21bcp435d-frontend-container
     ```
     ![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/runfront.png)

2. **Push to Docker Hub:**

   - Create repository in Docker Hub for Backend and Frontend
   - Push Frontend Docker image:
     ```bash
     docker tag 21bcp453d-frontend shingaladevarsh1/21bcp435d-frontend
     docker push shingaladevarsh1/21bcp435d-frontend
     ```
     ![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/uploadfront.png)
   - Push Backend Docker image:
     ```bash
     docker tag 21bcp453d-backend shingaladevarsh1/21bcp435d-backend
     docker push shingaladevarsh1/21bcp435d-backend
     ```
     ![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/uploadback.png)

3. **Images of Docker Hub:**

   - Repositories Images.
     ![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/hub.png)

4. **Access the Application:**

   Open your favorite browser and visit [http://localhost:80](http://localhost:80). Enjoy the application!
   ![Alt Text](https://raw.githubusercontent.com/sDevarsh/devarsh.io/master/images/website.png)

## Data Persistence

Data persistence is ensured by using Docker volumes. If the MySQL container is deleted, data remains available and is automatically added to a new Docker container by providing the same Docker volume.

Feel free to explore and modify the Dockerfiles to enhance your understanding of containerization and deployment! Happy coding! 🚀
