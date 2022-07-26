# dmc-codedeploy

Requisitos:
- Terraform 1.2.2
- Aws cli

Configurar:
```
$ aws configure
aws credentials:
aws access:
region: us-east-2
```

### Infrastructure as Code:
```
cd terraform/
cp ~/Downloads/Alo2.pem ./
# De ser necesario CAMBIAR los valores como name en terraform.tfvars
./terraform_apply.sh
```

Para eliminar:
```
./terraform_destroy.sh
```

### Deploy from localhost:
```
./scripts/aws_artifact_build 4
./scripts/aws_artifact_upload dmc-devops-code mario 4.zip
./scripts/aws_codedeploy_deployment draft-demo3-cd draft-demo3-dg dmc-devops-code mario 4.zip
```

### Deploy from Jenkins:
Create a jenkins job using Jenkinsfile
