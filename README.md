# Devops-Project
Devops Project React Application Deploy.

### Project Overview
This project is a React-based web application, showcasing a modern, responsive UI with features implemented using React. The app has been successfully deployed to an **AWS EC2** instance, making it accessible over the web. The project also involves automating build and deployment processes using **Docker** and **CI/CD pipelines**.

### Key Features:
- Frontend: Built with React.js to create an interactive and responsive user interface.
- Deployment: Hosted on AWS EC2 to ensure scalability and reliability.
- Containerization: The app is containerized using Docker for easier deployment and management.
- CI/CD Pipeline: Utilizes Jenkins for automating the deployment process, ensuring continuous integration and delivery.

---

## **Tech Stack**

- Frontend: React.js
- Deployment: AWS EC2
- Containerization: Docker
- CI/CD: Jenkins
- Version Control: Git

---

## **Dockerize the Image**
The Application is Dockerized to run on the containers with all the dependencies.
1. build the nodes.js using the node base image from the Dockerhub
2. copy the build to the Nginx image and trigger the build.
3. deploy it to the Required port which it needs to run.

## **Docker Hub Repo**
the DockerHub Registry is used to deploy the build image.
1. create a repo for both the Prod and Dev.
2. make the Repo Private or public as Required.
3. make the Docker Hub Tokens/Credentials are authorized to login to the repo.

## **Deployment on AWS EC2**

This application has been deployed to an AWS EC2 instance using the following steps:
1. Launch an EC2 instance with Ubuntu or your preferred OS.
2. SSH into the instance, install Node.js, and transfer the build files.
3. Use  Nginx to serve the app on EC2.
4. Optionally, configure Docker and Jenkins for continuous deployment.

---

## **CI/CD Pipeline**

Automated the deployment using Jenkins to enable continuous integration and continuous delivery:
- **Jenkins** automates the build process on each commit, pushing the Docker image to a registry, and deploying it on the EC2 instance.

## **Jenkins Build Pipeline**
1. create a Jenkins file as per the requirement.
2. clone the repo
3. I used multi-branch pipeline to trigger the build and push it to the repo.
4. use POll SCM to check the Repo for the changes for the auto build Trigger.
5. used Groovy script to run the build , and deploy the application.
---

## **Contributing**

Contributions are welcome! If you’d like to contribute, please follow these steps:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -m 'Add some feature'`).
4. Push the changes to your branch (`git push origin feature-branch`).
5. Open a pull request.

---

## **License**

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

## **Contact**

If you have any questions or suggestions, feel free to reach out:
- **Author**: Sridhar
- **GitHub**: [sridhar667](https://github.com/sridhar667)

---

