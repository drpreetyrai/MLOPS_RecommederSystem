
## create a virtual environments 

```bash
python -m venv venv

``` 

## Activate a virual environment

```bash
source venv/bin/activate


``` 


## Run setup.py file using
```bash

pip install -e .

``` 
![alt text](recommendation.png)


## use 

###  set GOOGLE_APPLICAT


gcloud auth application-default login


## DVC steps 
dvc add artifacts/raw
dvc add artifacts/processed/
dvc add artifacts/model
dvc add artifacts/model_checkpoint/
dvc add artifacts/weights/

## add to GCP Bucket 
dvc remote add -d myremote gs://my-dvc-bucket-9999

dvc status 

dvc push
dvc pull
 

## for docker 
docker build -t jenkins-dind . 

## for checking :- 
 docker images

## for running of container
docker run -d --name jenkins-dind ^



docker build -t jenkins-ml .
docker run -d -p 8080:8080 -p 50000:50000 --name jenkins-ml jenkins-ml
docker run -d -p 8080:8080 -p 50000:50000 -v $(pwd)/ml_project:/home/jenkins/ml_project --name jenkins-ml jenkins-ml

Access Jenkins at http://localhost:8080


