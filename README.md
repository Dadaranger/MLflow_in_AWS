### MLflow_in_AWS
#practice project using MLFLOW tracking service in AWS S3 and EC2

## MLFLOW on AWS Setup:

1. login to AWS console
2. create IAM user with AdministrationAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add security groups 5000 port

Run the following command on EC2 machine
```bash
sudo apt update

sudo apt install python3-pip

sudo apt install pipenv

sudo apt install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell

# then set aws credentials
aws configure

# finally 
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflowtrackinglei1

#set uri in your local terminal and in your code
export MLFLOW_TRACKING_URI=http://ec2-54-162-206-66.compute-1.amazonaws.com:5000/
