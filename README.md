# AWS LEARN

## AWS CONSOLE

Check parameters on AWS root AWS console

https://<YOUR URL AWS CONSOLE>.aws.amazon.com/console

1. Create user
  
https://console.aws.amazon.com/iam/home?region=us-east-1#/home
add user learn

2. Configure credentials in Sign-in credentials

Assigned MFA device

arn:aws:iam::xxxxxxxxxxxx:mfa/learn

 - Apply changes to use MFA (Generate token on mobile authenticator Google apps)

Access keys

-  Use access keys to make secure REST or HTTP Query protocol requests to AWS service APIs. For your protection, you should never share your secret keys with anyone. As a best practice, we recommend frequent key rotation.

SSH keys for AWS CodeCommit

- Use SSH public keys to authenticate access to AWS CodeCommit repositories
- Alert's if you lost this files dotn's possible login instance running

## Install awscli

[AWSCLI Install howto](http://docs.aws.amazon.com/cli/latest/userguide/installing.html)

## Provide credentials
```sh
$ aws configure
AWS Access Key ID []: KHJHJHJHVCVCVCLKJOUY
AWS Secret Access Key []: dljkhsdjhskjh786786/uhudhuhd
Default region name []: us-east-1
Default output format []: json
$
$ aws sts get-session-token --serial-number arn:aws:iam::849399717715:user/Claude --token-code 1234

OUTPUT
{
    "Credentials": {
        "SecretAccessKey": "dljkhsdjhskjh786786/uhudhuhd",
        "SessionToken": "Fdddn]][[]\\\\wEaDEbcjK18xhcrreP/JSKd87873IVPSGkL46vW+1xBVPNnBu31vBaNP7JICeKhxxtnWdfdfdfdfYBn3Pw56WSLoL92E/7b1EzsVpxIK6OVIUT454545JGgDRzbGVSk2mv0eiern+44444xQp1+Ypzuuuxxx0vFVw3EoBuuuuuuN7RiUz2D7IUUPwyd90vr/KnXru96ks4444JS53sgF",
        "Expiration": "2011-0`-14T11:53:56Z",
        "AccessKeyId": "KHJHJHJHVCVCVCLKJOUY"
    }
}
```

Export environments
```sh
$ export AWS_ACCESS_KEY=KHJHJHJHVCVCVCLKJOUY
$ export AWS_SECRET_ACCESS_KEY=dljkhsdjhskjh786786/uhudhuhd
$ export AWS_SESSION_TOKEN=Fdddn]][[]\\\\wEaDEbcjK18xhcrreP/JSKd87873IVPSGkL46vW+1xBVPNnBu31vBaNP7JICeKhxxtnWdfdfdfdfYBn3Pw56WSLoL92E/7b1EzsVpxIK6OVIUT454545JGgDRzbGVSk2mv0eiern+44444xQp1+Ypzuuuxxx0vFVw3EoBuuuuuuN7RiUz2D7IUUPwyd90vr/KnXru96ks4444JS53sgF
```

Configure credential files 
```sh
$ echo '
[mfa-role]
aws_access_key=KHJHJHJHVCVCVCLKJOUY
aws_secret_access_key=dljkhsdjhskjh786786/uhudhuhd
aws_session_token=Fdddn]][[]\\\\wEaDEbcjK18xhcrreP/JSKd87873IVPSGkL46vW+1xBVPNnBu31vBaNP7JICeKhxxtnWdfdfdfdfYBn3Pw56WSLoL92E/7b1EzsVpxIK6OVIUT454545JGgDRzbGVSk2mv0eiern+44444xQp1+Ypzuuuxxx0vFVw3EoBuuuuuuN7RiUz2D7IUUPwyd90vr/KnXru96ks4444JS53sgF
' >> ~/.aws/credentials
```

Add profile on config awscli

```sh
$ echo '
[profile mfa-role]
output = json
region = us-east-1
source-profile = mfa-role
'> ~/.aws/config 
```
## Compose json file example
```sh
$  echo
{
  "ImageId": "ami-80861296",
  "SecurityGroupIds": [ "sg-095234577" ],
  "InstanceType": "m3.medium",
  "SubnetId": "subnet-1db340dd55",
  "IamInstanceProfile": {
      "Arn": "arn:aws:iam::276376876983:instance-profile/learn"
  }
} > ec2-spot.json
```

## Deploy spot-instances
```sh
$ aws ec2 request-spot-instances --spot-price "0.010" --instance-count 1 --type "one-time" --launch-specification file://ec2-spot.json
```

# Automations next steps...

## Ansible

Provisioning sinatnces with ansible automations scripts.

[Ansible guide aws](http://docs.ansible.com/ansible/guide_aws.html)

## GIT

[Git Cheat Sheet](https://www.git-tower.com/blog/git-cheat-sheet/)

## Automatic documentation

[Lucidchart](https://www.lucidchart.com)

## Amazing notification tool

[Slack WebHooks](https://api.slack.com/incoming-webhooks)

Send notification to slack channels

```sh
$ aws ec2 request-spot-instances --spot-price "0.010" --instance-count 1 --type "one-time" --launch-specification file://ec2-spot.json |curl -X POST --data-urlencode 'payload={"channel": "#aws", "username": "webhookbot", "text": "AWS Spot Instance provision", "icon_emoji": ":ghost:"}' https://hooks.slack.com/services/T5sdsdFXs2/Bdfdfdf8DU/AdflkjJKKJkjdfdfdfEc44444v4444z
```