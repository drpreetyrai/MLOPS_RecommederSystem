
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





