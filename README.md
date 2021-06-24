# apprunner-nodejs-ecr

## Create ECR

```sh
aws ecr create-repository --repository-name app-runner-example --image-scanning-configuration scanOnPush=true --profile <AWS_PROFILE> --region us-east-1
```

## Login to Docker

```sh
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <AWS-ACCOUNT-ID>.dkr.ecr.us-east-1.amazonaws.com

```

## Tag docker image

```sh
docker tag app-runner:1 <AWS-ACCOUNT-ID>.dkr.ecr.us-east-1.amazonaws.com/app-runner-example

```

## Push to ECR

```sh
docker push <AWS-ACCOUNT-ID>.dkr.ecr.us-east-1.amazonaws.com/app-runner-example

```
