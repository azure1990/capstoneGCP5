# capstoneGCP5
Project for bootcamp

- We cloned the repository https://github.com/GNiruthian/Europe-Travel-Website-html-css-js
- We created the image locally with Docker. First the Dockerfile:


FROM nginx
COPY Europe-Travel-Website-html-css-js  /usr/share/nginx/html

- Once created, we run the following command:

docker build -t NAME_YOU_WANT_FOR_YOUR_IMAGE

- Next we uploaded the image to Docker hub (this was an extra step on our behalf):
Steps on this link https://docs.docker.com/get-started/04_sharing_app/

- Create the repository on Registry:

gcloud artifacts repositories create [REPO_NAME] — repository-format=docker \
— location=[REGION] — description=”My Artifact Repository”

- Now on the GCP CLI, we proceeded to pull the image from our Docker Hub rep, create the image for the Registry and then deploy the image with GKE

- Docker pull:

docker pull robscode/101capstonegcp

- Create repository image:

docker tag [IMAGE_NAME] gcr.io/[PROJECT_ID]/[REPO_NAME]/[IMAGE_NAME]:[TAG]

- Authenticated docker on the CLI:

gcloud auth configure-docker


- Push the image to the repository we created on Registry:

docker push gcr.io/elsalgroup5/capstonegcp/capstonegcp5:final

- Deployed to GKE using the GUI on the Google Cloud Console. 

- Created the git log file with the command:

git --no-pager log > file.log

