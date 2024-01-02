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