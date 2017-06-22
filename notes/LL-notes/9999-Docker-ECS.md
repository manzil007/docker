# Docker and AWS ECS

- Steps to add ECS account through AWSCLI and push/pull docker image

```
apt-get update && apt-get install -y apt-transport-https ca-certificates
apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
echo deb https://apt.dockerproject.org/repo ubuntu-trusty main > /etc/apt/sources.list.d/docker.list
apt-get update && apt-get install -y docker-engine
gpasswd -a ubuntu docker
docker pull ubuntu:14.04
curl 'https://s3.amazonaws.com/aws-cli/awscli-bundle.zip' -o 'awscli-bundle.zip'
unzip awscli-bundle.zip && ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws
eval '$(aws ecr get-login --region us-east-1 --registry-ids XXXXXXXXXXXX)'
export AWS_ACCESS_KEY_ID=-x-x-x-x-x-x-x-
export AWS_SECRET_ACCESS_KEY=-x-x-x-x-x-x-x-x-x-x-x-x-x-
eval '$(aws ecr get-login --region us-east-1 --registry-ids XXXXXXXXXXXX)'
docker pull XXXXXXXXXXXX.dkr.ecr.us-east-1.amazonaws.com/services-base:0.3.0
cd
ps fauwx | less
which docker
docker ps
docker images
```

```
To install the AWS CLI and Docker and for more information on the steps below, visit the ECR documentation page.
1) Retrieve the docker login command that you can use to authenticate your Docker client to your registry: 
Note: 
If you receive an "Unknown options: --no-include-email" error, install the latest version of the AWS CLI. Learn more
aws ecr get-login --no-include-email --region us-east-1
2) Run the docker login command that was returned in the previous step. 
Note: 
If you are using Windows PowerShell, run the following command instead.
Invoke-Expression -Command (aws ecr get-login --no-include-email --region us-east-1)
3) Build your Docker image using the following command. For information on building a Docker file from scratch see the instructions here. You can skip this step if your image is already built:
docker build -t sysops-reports .
4) After the build completes, tag your image so you can push the image to this repository:
docker tag sysops-reports:latest 104966627370.dkr.ecr.us-east-1.amazonaws.com/sysops-reports:latest
5) Run the following command to push this image to your newly created AWS repository:
docker push 104966627370.dkr.ecr.us-east-1.amazonaws.com/sysops-reports:latest
```
