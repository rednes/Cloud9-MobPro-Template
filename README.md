# Cloud9-MobPro-Template

AWS Cloud9でモブプログラミングの環境を作るための、CloudFormationテンプレートです。

## Overview

![構成図](https://github.com/rednes/Cloud9-MobPro-Template/blob/master/img/overview.png?raw=true)

## Requirements

- awscli(1.15 later)

## Usages

```
$ export AWS_DEFAULT_PROFILE=YOUR_PROFILE
$ export AWS_DEFAULT_REGION=us-west-2
$ aws cloudformation create-stack --template-body file://./template.yml --stack-name Cloud9-MobPro-Template --capabilities CAPABILITY_NAMED_IAM
$ aws cloudformation wait stack-create-complete --stack-name Cloud9-MobPro-Template
$ SHARECOMMAND=$(echo $(aws cloudformation describe-stacks --stack-name Cloud9-MobPro-Template --query "Stacks[0].Outputs[0].OutputValue")|tr -d '"') && eval $SHARECOMMAND
```
