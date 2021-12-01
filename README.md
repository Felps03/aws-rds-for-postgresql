# aws-rds-for-postgresql

## Dependencies

 - Git
 - AWS CLI

##   Deploy the resources in your AWS environment

###   Create the ssm parameters

> :warning: Pay attention to the region where your aws cli is configured
> :warning: Be sure to run the following command in the root directory
> :warning: Before running the following command, go to the ssm-parameters script and replace the value "your@mail.com" with a desired email address

```bash
sh ./parameters/ssm-parameters
```

### Deploy RDS alert event

> :warning: Be sure to run the following command in the root directory

#### Deploy in your default AWS region

```bash
aws cloudformation create-stack --stack-name RDSEventDemoStack --template-body file://cloudformation-templates/rds-alert-event.yaml
```

####   Deploy in a given region

```bash
aws cloudformation create-stack --stack-name RDSEventDemoStack --region <YOUR-CHOSEN-REGION> --template-body file://cloudformation-templates/rds-alert-event.yaml
```

### Deploy RDS for PostgreSQL

> :warning: Be sure to run the following command in the root directory

#### Deploy in your default AWS region

```bash
aws cloudformation create-stack --stack-name RDSDemoStack --template-body file://cloudformation-templates/rds-for-postgresql.yaml
```

####   Deploy in a given region

```bash
aws cloudformation create-stack --stack-name RDSDemoStack --region <YOUR-CHOSEN-REGION> --template-body file://cloudformation-templates/rds-for-postgresql.yaml
```