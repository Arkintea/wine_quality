# End-to-end-ML-Project


## Workflows

1. update config.yaml
2. update schema.yaml
3. update params.yaml
4. update the entity
5. update the configuration manager in src config
6. update the components
7. update the pipeline
8. update the main.py
9. update the app.py


## ENVIRONMENT SETUP
Creating conda environment
```
conda create -n wine_quality python=3.8 -y
```

Activate conda environment
```
conda activate wine_quality
```
OR
```
conda activate wine_quality/
```

Install requirements
```
pip install -r requirements.txt
```

## GIT
To add file to git
```
git add <filename>
```
OR
```
git add .
```

```
Note: To ignore file or folder from git we can write the name of the file/folder in .gitignore folder
```

To check status
```
git status
```

To check all versions maintained by git
```
git log
```

To create version/commit all changes by git
```
git commit -m "message"
```

To send version/changes to github
```
git push origin main
```

To check remote url
```
git remote -v
```


## BUILD DOCKER IMAGE
```
docker build -t <image_name>:<tagname> .
```
Note: Image name for docker must be lowercase
```
To list docker image
```
docker images
```
Run docker image
```
docker run -p 5000:5000 -e PORT=5000 f8c749e73678
```
To check running container in docker
```
docker ps
```
To stop docker conatiner
```
docker stop <container_id>
```
To install ipykernel
```
install ipykernel
```
-e . 
means install all packages in current directory
setup.py is required whenever you want to install -e .
```


## AWS-CICD-DEPLOYMENT-WITH-GITHUB-ACTION


1. Login to AWS console.
2. Create IAM user for deployment

    ```
	# Policy:
	1. AmazonEC2ContainerRegistryFullAccess
	2. AmazonEC2FullAccess

	# with specific access
	1. EC2 access : It is virtual machine
	2. ECR: Elastic Container registry to save your docker image in aws

	# Description: About the deployment
	1. Build docker image of the source code
	2. Push your docker image to ECR
	3. Launch Your EC2 
	4. Pull Your image from ECR in EC2
	5. Lauch your docker image in EC2
    ```


3. Create ECR repo to store/save docker image
    - Save the URI: 058264250048.dkr.ecr.eu-west-2.amazonaws.com/wine_quality_project
4. Create EC2 machine (Ubuntu) 
5. Open EC2 and Install docker in EC2 Machine:

	```
	# optional
	1. sudo apt-get update -y
	2. sudo apt-get upgrade
	
	# required
	3. curl -fsSL https://get.docker.com -o get-docker.sh
	4. sudo sh get-docker.sh
	5. sudo usermod -aG docker ubuntu
	6. newgrp docker
	
6. Configure EC2 as self-hosted runner:
    - setting> actions> runner> new self hosted runner> choose os> then run command one by one
7. Setup github secrets:
    ```
    - AWS_ACCESS_KEY_ID=
    - AWS_SECRET_ACCESS_KEY=
    - AWS_REGION = us-east-1
    - AWS_ECR_LOGIN_URI = demo>>  058264250048.dkr.ecr.eu-west-2.amazonaws.com
    - ECR_REPOSITORY_NAME = simple-app
    ```

git config --global user.name "arkintea"