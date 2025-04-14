SIT323 Task 5.2D – Dockerization & Publishing Microservice to Google Cloud

## Project Overview

This task involves preparing a Node.js microservice for production by:
- Dockerizing the app
- Publishing the Docker image to a private Google Cloud Container Registry
- Testing the image by running it from the cloud
- Pushing the complete project to GitHub for version control



##  Dockerization Steps

### 1. Build the Docker image

docker build -t microservice .

2. Tag the Docker image for GCP

docker tag microservice gcr.io/sit323-25t1-weerasuriy-b91fd7c/microservice

Google Cloud Setup
3. Authenticate Google Cloud
gcloud auth login
gcloud config set project sit323-25t1-weerasuriy-b91fd7c
Also enable the Container Registry API through the Google Cloud Console.

4. Configure Docker to use GCP

gcloud auth configure-docker

Push Docker Image to Google Cloud
5. Push image to Container Registry
docker push gcr.io/sit323-25t1-weerasuriy-b91fd7c/microservice

Test the Deployment
6. Pull the image from the registry
docker pull gcr.io/sit323-25t1-weerasuriy-b91fd7c/microservice

7. Run the image locally from GCP
docker run -p 3000:3000 gcr.io/sit323-25t1-weerasuriy-b91fd7c/microservice
Access the running app at:
http://localhost:3000

GitHub Push Instructions
8. Push your code to GitHub
git init
git remote add origin https://github.com/DanishaRodrigo/sit323-2025-prac5d.git

git add .
git commit -m "Dockerization and GCP publishing"
git branch -M main
git push -u origin main

Name: Weerasuriya Ararchchige Danisha Vishvani Rodrigo
Student ID: s224731771
