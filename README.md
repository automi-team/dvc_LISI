# DVC Storage using S3 

***Note :  This dvc usage is not clean, following work will be cleaner*** 


## Initialize 
* Installl DVC and its dependencies 
    ```console
    pip install 'dvc[s3]'
    ````
* Initialize dvc repo 
    If no github repository in already initlialize, do 
    ```console 
    git init
    ```
    ```console
    dvc init
    ```
* Add remote storage 
    ```console 
    dvc remote add -d storage s3://automi-dvc....
    ````

## Prepare data and connect to AWS 
* Download data to folders 
    ```console
    wget https://automi-dvc.s3....
    unzip folder.zip
    mkdir folder 
    mv images/ folder/
    mv labels/ folder/ 
* Configure AWS with keys 
    ```console 
    dvc remote modifiy --local storage access_key_id 'YOUR_ACCESS_KEY'
    dvc remote modifiy --local storage secret_access_key 'YOUR_SECRET_ACCESS_KEY'
    ```
* Push to dvc 
    ```console 
    dvc push 
    ```
