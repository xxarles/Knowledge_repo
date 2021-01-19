#AWS-CLI setup

To install: 
```sudo apt-get install aws-cli```

To configure
```aws configure --profile <profile_name>```

#Docker ECR 
```aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin <accountID>.dkr.ecr.us-east-2.amazonaws.com```

Creating repo
```
aws ecr create-repository \
        --repository-name <proj_name> \
        --image-scanning-configuration scanOnPush=true \
        --region us-east-2
```
Uploading this repo

```docker tag l_n_ner:latest 949145459004.dkr.ecr.us-east-2.amazonaws.com/l_n_ner:latest

docker push 949145459004.dkr.ecr.us-east-2.amazonaws.com/l_n_ner:latest```
