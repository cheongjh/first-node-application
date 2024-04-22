#  Steps to create an image and deploy to AWS ECR

1. Retrieve an authentication token and authenticate your Docker client to your registry.
Use the AWS CLI:

`aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 255945442255.dkr.ecr.us-east-1.amazonaws.com`

Note: If you receive an error using the AWS CLI, make sure that you have the latest version of the AWS CLI and Docker installed.

2. Build your Docker image using the following command. For information on building a Docker file from scratch see the instructions here . You can skip this step if your image is already built:

`docker build -t node-docker-leon .`

3. After the build completes, tag your image so you can push the image to this repository:

`docker tag node-docker-leon:latest 255945442255.dkr.ecr.us-east-1.amazonaws.com/node-docker-leon:latest`

4. Run the following command to push this image to your newly created AWS repository:

`docker push 255945442255.dkr.ecr.us-east-1.amazonaws.com/node-docker-leon:latest`

#  Steps to run ECR image

`docker run -d -p 8080:3000 255945442255.dkr.ecr.us-east-1.amazonaws.com/node-docker-leon:latest`

![image](https://github.com/cheongjh/first-node-application/assets/15931746/4d721a09-8459-4a2a-b353-648dc5e04bcc)

![image](https://github.com/cheongjh/first-node-application/assets/15931746/87fa5407-417f-496a-b102-2b736af4c2a8)
