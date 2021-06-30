# apprunner-nodejs-ecr

## Create ECR

```sh
aws ecr create-repository --repository-name app-runner-example --image-scanning-configuration scanOnPush=true --profile <AWS_PROFILE> --region us-east-1
```

## Login to Docker

```sh
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <AWS-ACCOUNT-ID>.dkr.ecr.us-east-1.amazonaws.com

```

## Build Docker image

```sh
docker build -t app-runner:1 .
```

## Tag docker image

```sh
docker tag app-runner:1 <AWS-ACCOUNT-ID>.dkr.ecr.us-east-1.amazonaws.com/app-runner-example

```

## Push to ECR

```sh
docker push <AWS-ACCOUNT-ID>.dkr.ecr.us-east-1.amazonaws.com/app-runner-example

```

## Create App Runner through One Click CloudFormation Deployment

<p align="center">
  <a href="https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/template?stackName=AppRunnerExample&templateURL=https://antstack-opensource.s3.amazonaws.com/aws-apprunner/create-apprunner.yml" target="_blank" rel="noopener noreferrer">
    <img border="0" alt="Click to Deploy to Cloudformation" src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png">
  </a>
</p>
